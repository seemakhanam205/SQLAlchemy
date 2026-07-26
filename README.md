# SQLAlchemy Core CRUD Operations with PostgreSQL

A beginner-friendly project demonstrating how to perform **CRUD (Create, Read, Update, Delete)** operations using **SQLAlchemy Core** with a **PostgreSQL** database.

## 📌 Features

- Connect to PostgreSQL using SQLAlchemy
- Create tables using SQLAlchemy Core
- Insert records into a table
- Read records from the database
- Update existing records
- Delete records
- Execute SQL queries without writing raw SQL

---

## 🛠️ Technologies Used

- Python 3.x
- SQLAlchemy
- PostgreSQL
- Psycopg (PostgreSQL Driver)

---

## 📂 Project Structure

```
.
├── core.py          # Main Python file containing CRUD operations
└── README.md
```

---

## 📋 Database Schema

### Table: `people`

| Column | Data Type | Description |
|--------|-----------|-------------|
| id | Integer | Primary Key |
| name | String | Name of the person |
| age | Integer | Age of the person |

---

## 🚀 Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/sqlalchemy-crud.git
cd sqlalchemy-crud
```

### 2. Create a virtual environment (Optional)

```bash
python -m venv venv
```

Activate it:

Windows

```bash
venv\Scripts\activate
```

Linux/Mac

```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install sqlalchemy psycopg
```

---

## ⚙️ Configure PostgreSQL

Update the connection string in `core.py`:

```python
engine = create_engine(
    "postgresql+psycopg://username:password@localhost:5432/database_name",
    echo=True
)
```

Replace:

- `username`
- `password`
- `database_name`

with your PostgreSQL credentials.

---

## ▶️ Run the Project

```bash
python core.py
```

---

# CRUD Operations

## Create

Insert a new record into the database.

```python
insert_statement = people.insert().values(
    name="Zaeema",
    age=40
)

conn.execute(insert_statement)
conn.commit()
```

---

## Read

Retrieve all records.

```python
select_statement = people.select()

result = conn.execute(select_statement)

for row in result:
    print(row)
```

---

## Update

Update an existing record.

```python
update_statement = (
    people.update()
    .where(people.c.name == "Seema")
    .values(age=21)
)

conn.execute(update_statement)
conn.commit()
```

---

## Delete

Delete records from the table.

```python
delete_statement = (
    people.delete()
    .where(people.c.name == "Seema")
)

conn.execute(delete_statement)
conn.commit()
```

---

## 📖 SQLAlchemy Concepts Covered

- `create_engine()`
- `MetaData`
- `Table`
- `Column`
- SQLAlchemy Data Types
- `create_all()`
- `insert()`
- `select()`
- `update()`
- `delete()`
- `where()`
- `values()`
- `execute()`
- `commit()`
- Table Columns (`people.c.column_name`)

---

## 📚 Learning Objectives

This project helps understand:

- SQLAlchemy Core architecture
- How Python communicates with PostgreSQL
- Mapping SQL queries to SQLAlchemy methods
- CRUD operations using SQLAlchemy Core
- Transaction management using `commit()`

---

## Sample Output

```
(1, 'Seema', 21)
(2, 'Zaeema', 40)
```

---

## Future Improvements

- SQLAlchemy ORM implementation
- Filtering using multiple conditions
- Ordering and limiting results
- Aggregate functions (`COUNT`, `SUM`, `AVG`)
- Transactions and rollback
- Exception handling
- Connection pooling
- Relationships between tables
- Flask/FastAPI integration

---

## Author

**Seema Khanam**

Computer Science Engineering Student

Learning Backend Development with Python, PostgreSQL, and SQLAlchemy.
