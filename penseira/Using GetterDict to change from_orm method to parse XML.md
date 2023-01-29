29/01/2023 20:36

In the code below, we create a `UserGetter` class, child of Pydantic's `Getter Dict`. The `get` method from `Getter Dict` class runs everytime a Pydantic object processes an arbitrary class (like in `from_orm` method). Using our `UserGetter` class we can customize a `from_orm` method to, for example, parse XML data to create Pydantic class object.

```python
from pydantic import BaseModel
from typing import Any
from pydantic.utils import GetterDict
from xml.etree.ElementTree import fromstring


xmlstring = """
<User Id="2138">
    <FirstName>André<FirstName/>
    <LoggedIn Value="true" />
</User>
"""


class UserGetter(GetterDict):

    def get(self, key: str, default: Any) -> Any:

        # element attributes
        if key in {'Id', 'Status'}:
            return self._obj.attrib.get(key, default)

        # element children
        else:
            try:
                return self._obj.find(key).attrib['Value']
            except (AttributeError, KeyError):
                return default


class User(BaseModel):
    Id: int
    Status: str | None
    FirstName: str | None
    LastName: str | None
    LoggedIn: bool

    class Config:
        orm_mode = True
        getter_dict = UserGetter


user = User.from_orm(fromstring(xmlstring))
```

Tags:



---
# References

