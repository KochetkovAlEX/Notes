# Pydantic
### 1. Базовая валидация
Особенностью данной библиотеки является то, что для работы исходные данные нужно обернуть в класс, поля которого соответствуют определенному типу.

```python
from pydantic import BaseModel


data = {
	"age": 12,
	"name": "Alex"
}


class User(BaseModel):
	age: int
	name: str


user = User(**data)
print(user)
```

### 2. "Жесткая" валидация

```python
from pydantic import BaseModel, Field


data = {
	"age": 12,
	"name": "Alex"
}


class User(BaseModel):
	age: int | None = Field(max_length=100)
	name: str = Field(ge=0, le=130)


user = User(**data)
print(user)
```

>**Field** - поле с дополнительными параметрами.   
> ge, le = больше/меньше чем - дополнительные параметры   

**Особенности:**  
+ Поддерживает наследование
+ Игнор данных, которые не требуются

```python
from pydantic import BaseModel, ConfigDict


data = {
	"age": 12,
	"name": "Alex",
	"gender": "male"
}


class User(BaseModel):
	age: int | None = Field(max_length=100)
	name: str = Field(ge=0, le=130)

	model_config = ConfigDict(extra='forbid') # Запрет дополнительных данных


user = User(**data)
print(user)
```

# FastAPI + Pydantic

```python
from pydantic import BaseModel, ConfigDict

from fastapi import FastAPI


app = FastAPI()

data = {
	"age": 12,
	"name": "Alex"
}


class User(BaseModel):
	age: int | None = Field(max_length=100)
	name: str = Field(ge=0, le=130)

	model_config = ConfigDict(extra='forbid') # Запрет дополнительных данных


users = []


@app.post('/users')
def add_user(user: User):
	users.append(user)
	return {"status": 200}

```
