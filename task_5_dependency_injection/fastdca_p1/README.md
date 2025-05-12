# 🚀 FastAPI Dependency Injection Project

Yeh project FastAPI framework ka use karta hai jisme **Dependency Injection** ke multiple examples diye gaye hain — simple, query parameters ke sath, multiple dependencies, aur custom class-based dependencies.

---

## 📦 Required Libraries

- Python 3.10 or above
- FastAPI
- Uvicorn

**Install FastAPI & Uvicorn:**
```bash
pip install fastapi uvicorn
▶️ Server Run Karne Ka Tarika
bash
Copy
Edit
uvicorn main:app --reload
Visit Swagger Docs: http://127.0.0.1:8000/docs

🧪 API Endpoints Explanation
1. /get-simple-goal
Simple dependency return karta hai ek goal.

Method: GET

Response:

json
Copy
Edit
{ "goal": "We are building AI Agents Workforce" }
2. /get-goal?username=Shaheena
Dependency ke through username accept karta hai.

Method: GET

Response:

json
Copy
Edit
{
  "goal": "We are building AI Agents Workforce",
  "username": "Shaheena"
}
3. /signin?username=admin&password=admin
Query parameters ke through login system.

Agar username = admin aur password = admin ho to successful.

Response:

json
Copy
Edit
{ "message": "Login Successful" }
Ya agar galat ho to:

json
Copy
Edit
{ "message": "Login Failed" }
4. /main/{num}
Path parameter num + 2 dependencies:

depfunc1 -> num + 1

depfunc2 -> num + 2

Total = num + num1 + num2

Example:

text
Copy
Edit
Pakistan 18
5. /blog/{id}
Blog ID ke through blog ka naam return karta hai.

Agar ID exist nahi karti to 404 error deta hai.

Example:

json
Copy
Edit
"Machine Learning Blog"
6. /user/{id}
User ID ke through user ka naam return karta hai.

Agar user ID galat ho to 404 error deta hai.

Example:

json
Copy
Edit
"Mohammed"
📚 Concepts Covered
✅ FastAPI Dependency Injection using Depends

✅ Use of Annotated for type-safe dependency injection

✅ Query Parameters handling

✅ Class-based custom dependency injection

✅ Multiple Dependencies injection

✅ Error handling with HTTPException

📁 Project Structure
bash
Copy
Edit
📦 your-project/
├── main.py          # FastAPI code
└── README.md        # Documentation file
👩‍💻 Author
Created by Shaheena Nazeer
Learning FastAPI Dependency Injection — Baby Steps Approach 👶

yaml
Copy
Edit

---

Aap is content ko copy karke apne folder mein `README.md` naam se ek file bana kar paste kar dijiye. Agar diagram bhi chahiye to main bana kar de sakta hoon — bas bata dijiye.







