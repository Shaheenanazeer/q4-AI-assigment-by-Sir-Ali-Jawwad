# FastDCA Project - Task 1 (Generative AI)

This is a simple FastAPI project created as part of the Generative AI assignment. It includes two GET API routes: one for the root path and one with a path and query parameter.

---

## 🚀 Getting Started

### Prerequisites

- Python 3.11 or above
- [uv](https://github.com/astral-sh/uv) (for managing environment and dependencies)

---

### 📁 Project Setup

1. **Initialize the Project:**

```bash
uv init fastdca-p1
cd fastdca-p1
Create & Activate Virtual Environment:

On macOS/Linux:

bash
Copy
Edit
uv venv
source .venv/bin/activate
On Windows:

bash
Copy
Edit
uv venv
.venv\Scripts\activate
Install Dependencies:

bash
Copy
Edit
uv add "fastapi[standard]"
uv add --dev pytest pytest-asyncio
🧪 API Endpoints
1. Root Endpoint
URL: /

Method: GET

Response:

json
Copy
Edit
{
  "Hello": "World"
}
2. Item Endpoint
URL: /items/{item_id}

Method: GET

Path Parameter:

item_id (integer)

Query Parameter (optional):

q (string)

Example: /items/5?q=test

Response:

json
Copy
Edit
{
  "item_id": 5,
  "q": "test"
}
▶️ Run the Server
bash
Copy
Edit
fastapi dev main.py
OR

bash
Copy
Edit
uv run uvicorn main:app --host 0.0.0.0 --port 8000 --reload
🔍 Test in Browser
Open API Root: http://127.0.0.1:8000

Interactive Docs (Swagger): http://127.0.0.1:8000/docs

🧾 Project Info
Name: fastdca-p1

Framework: FastAPI

Server: Uvicorn

Testing: Pytest, pytest-asyncio

📌 Notes
Use fastapi dev only for development mode.

Do not install FastAPI globally when using uv.

yaml
Copy
Edit

---









