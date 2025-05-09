# DACA Chatbot API

This is a FastAPI-based chatbot API created for the DACA tutorial series. It demonstrates how to use **Pydantic** models, including:

* Simple model validation
* Nested models
* Optional fields
* Built-in and custom validators

It also includes working examples of FastAPI endpoints and custom metadata handling.

---

## 🚀 Features

* FastAPI web framework
* Pydantic models for user and message validation
* Nested model structures (Address, Metadata)
* Custom field validation for name length
* Metadata auto-generation using `datetime` and `uuid4`

---

## 📦 Requirements

* Python 3.10 or higher
* fastapi
* uvicorn
* pydantic\[email]

---

## ⚙️ Setup Instructions

```bash
# Create virtual environment
python -m venv .venv

# Activate virtual environment
# On Windows PowerShell:
. .venv\Scripts\Activate
# On Unix/macOS:
source .venv/bin/activate

# Install dependencies
pip install fastapi uvicorn pydantic[email]
```

---

## ▶️ Running the App

```bash
uvicorn main:app --reload
```

Open your browser at:

* Swagger Docs: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)

---

## 📚 Pydantic Models

### Basic Model

```python
class User(BaseModel):
    id: int
    name: str
    email: str
    age: int | None = None
```

### Nested Model

```python
class Address(BaseModel):
    street: str
    city: str
    zip_code: str

class UserWithAddress(BaseModel):
    id: int
    name: str
    email: EmailStr
    addresses: list[Address]
```

### Custom Validator

```python
@validator("name")
def name_must_be_at_least_two_chars(cls, v):
    if len(v) < 2:
        raise ValueError("Name must be at least 2 characters long")
    return v
```

### Metadata Model

```python
class Metadata(BaseModel):
    timestamp: datetime = Field(default_factory=lambda: datetime.now(tz=UTC))
    session_id: str = Field(default_factory=lambda: str(uuid4()))
```

---

## 📡 API Endpoints

### `GET /`

Returns a welcome message.

### `GET /users/{user_id}`

Returns a user ID and optional role.

### `POST /chat/`

Receives a message and returns a chatbot response with metadata.

Request body:

```json
{
  "user_id": "abc123",
  "text": "Hello!",
  "metadata": { "timestamp": "auto", "session_id": "auto" },
  "tags": ["greeting"]
}
```

---

## 👩‍💻 Author

Developed by Shaheena Nazeer for the DACA tutorial series.

---


