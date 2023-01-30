30/01/2023 17:18

Tags: [[Python]] [[Pydantic]]

To create a custom validation for a field in a Pydantic model, you do something like this:

```python
from pydantic import BaseModel, ValidationError, validator


class Person(BaseModel):
    name: str
    age: int

    @validator("age")
    def age_less_than_150_years(cls, v):
        if v >= 150:
            raise ValueError("age must be less than 150 years")
        return v


try:
    Person(name="André", age=250)
except ValidationError as e:
    print(e.errors())
```

This will raise a `ValueError`:

```json
[
	{
	'loc': ('age',), 
	'msg': 'age must be less than 150 years', 
	'type': 'value_error'
	}
]
```

---
# References

https://docs.pydantic.dev/usage/models/