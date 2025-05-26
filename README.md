# 📰 Articles & Magazines Relationship Project

This is a Python and SQL-based system modeling the relationships between **Authors**, **Articles**, and **Magazines**.

## 📘 Project Description

This project demonstrates object relationships using Python OOP and SQL. It implements the following:

- An **Author** can write many **Articles**
- A **Magazine** can publish many **Articles**
- An **Article** belongs to both an **Author** and a **Magazine**
- The **Author-Magazine** relationship is many-to-many through **Articles**

## 🧱 Technologies Used

- Python 3
- SQLite (via `sqlite3`)
- Pytest for unit testing
- Raw SQL queries for data persistence

---

## 📁 Project Structure

```bash
code-challenge/
├── lib/
│   ├── models/
│   │   ├── author.py
│   │   ├── article.py
│   │   └── magazine.py
│   ├── db/
│   │   ├── connection.py
│   │   ├── schema.sql
│   │   └── seed.py
│   ├── debug.py
│   └── __init__.py
├── tests/
│   ├── test_author.py
│   ├── test_article.py
│   └── test_magazine.py
├── scripts/
│   ├── setup_db.py
│   └── run_queries.py
├── .gitignore
├── README.md
└── Pipfile / requirements.txt
🛠️ Setup Instructions
📦 Option 1: Pipenv (Recommended)
bash
Copy
Edit
pip install pipenv
pipenv install pytest sqlite3
pipenv shell
🧪 Option 2: venv
bash
Copy
Edit
python -m venv env
source env/bin/activate        # On Mac/Linux
# OR
env\Scripts\activate           # On Windows

pip install pytest
🗃️ Database Setup (SQLite)
Edit lib/db/connection.py:

python
Copy
Edit
import sqlite3

def get_connection():
    conn = sqlite3.connect('articles.db')
    conn.row_factory = sqlite3.Row
    return conn
Then run:

bash
Copy
Edit
python scripts/setup_db.py
This will:

Create the database

Apply the schema

Seed it with initial data

🚀 Running the Project
Start an interactive debugging session:

bash
Copy
Edit
python lib/debug.py
Run all tests:

bash
Copy
Edit
pytest
✅ Features Implemented
Create, find, and query Authors, Articles, and Magazines

SQL-backed relationships between all objects

Complex queries (e.g., authors with most articles, magazines with 2+ authors, etc.)

Transaction-safe inserts

🧪 Testing
Test files are located in the tests/ directory.

To run all tests:

bash
Copy
Edit
pytest
📝 Author Class Responsibilities
Save/find authors

List articles by author

List magazines contributed to

Add article

Get topic areas (unique magazine categories)

🗞️ Magazine Class Responsibilities
Save/find magazines

List all articles in magazine

List all contributors

List contributing authors (with >2 articles)

List article titles

✍️ Article Class Responsibilities
Save/find articles

Link to author and magazine

