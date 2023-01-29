25/01/2023 20:00

Tags: [[Pydantic]] [[SQLAlchemy]]

Consider the following code:

```python
from typing import List
from sqlalchemy import Column, Integer, String
from sqlalchemy.dialects.postgresql import ARRAY
from sqlalchemy.ext.declarative import declarative_base
from pydantic import BaseModel, constr

Base = declarative_base()


class UserORM(Base):
    __tablename__ = 'companies'
    id = Column(Integer, primary_key=True, nullable=False)
    name = Column(String(63), unique=True)


class UserModel(BaseModel):
    id: int
    name: constr(max_length=63)

    class Config:
        orm_mode = True


user_orm = UserORM(
    id=123,
    name='Testing',
)

print(user_orm)
#> <models_orm_mode.UserORM object at 0x7f395d48fbe0>

user_model = UserModel.from_orm(user_orm)

print(user_model)
#> id=123 name='Testing'
```

So, `class Config` is used to set the `orm_mode` value to `True`. With that we can use the `from_orm` method to map all values from the SQLAlchemy ORM model to our own Pydantic model.

---
# References

https://docs.pydantic.dev/usage/models/