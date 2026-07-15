# FastAPI Blog

A simple blog application built while learning **FastAPI**, **SQLAlchemy**, and **SQLite**. This project started with an in-memory data store and was gradually upgraded to use a real database and proper CRUD operations.

The goal of this project is to understand how modern backend applications are structured and how FastAPI handles request validation, dependency injection, database interactions, and HTML rendering.

---

## Features

- Create, Read, Update, and Delete (CRUD) operations
- Full (`PUT`) and Partial (`PATCH`) updates
- User and Post management
- SQLite database with SQLAlchemy ORM
- Request and Response validation using Pydantic
- Jinja2 templates for server-side rendered pages
- Static file support
- Automatic API documentation with Swagger UI

---

## Tech Stack

- Python 3
- FastAPI
- SQLAlchemy
- SQLite
- Pydantic
- Jinja2
- Uvicorn

---

## Project Structure

```text
fastapi-blog/
│
├── static/              # Static assets
├── templates/           # HTML templates
│
├── database.py          # Database configuration
├── models.py            # SQLAlchemy models
├── schemas.py           # Pydantic schemas
├── main.py              # Application entry point
│
├── requirements.txt
└── README.md
```

---

## API Endpoints

### Posts

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/posts` | Get all posts |
| GET | `/api/posts/{post_id}` | Get a single post |
| POST | `/api/posts` | Create a new post |
| PUT | `/api/posts/{post_id}` | Replace a post |
| PATCH | `/api/posts/{post_id}` | Update selected fields of a post |
| DELETE | `/api/posts/{post_id}` | Delete a post |

### Users

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/users` | Get all users |
| GET | `/api/users/{user_id}` | Get a single user |
| POST | `/api/users` | Create a new user |
| PATCH | `/api/users/{user_id}` | Update user details |
| DELETE | `/api/users/{user_id}` | Delete a user |

---

## What I Learned

This project helped me understand:

- FastAPI routing
- Path and query parameters
- Request and response validation
- Pydantic schemas
- SQLAlchemy ORM
- SQLite integration
- Dependency Injection using `Depends()`
- Database sessions
- Model relationships
- One-to-Many relationships
- Cascade deletes
- Jinja2 templating
- HTTP status codes
- REST API design
- PUT vs PATCH
- Error handling with `HTTPException`

---

## Database Models

### User

- id
- username
- email
- image_file

### Post

- id
- title
- content
- user_id

Relationship:

```text
User (1)
   │
   └──────────────► Post (Many)
```

A user can have multiple posts, and deleting a user also deletes all of their posts using SQLAlchemy's cascade behavior.

---

## Running the Project

### Clone the repository

```bash
git clone https://github.com/visheshbpatel/fastapi-blog.git
```

### Move into the project

```bash
cd fastapi-blog
```

### Create a virtual environment

```bash
python -m venv .venv
```

### Activate it

**Windows**

```bash
.venv\Scripts\activate
```

**Linux / macOS**

```bash
source .venv/bin/activate
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Start the development server

```bash
uvicorn main:app --reload
```

---

## API Documentation

After running the server, FastAPI automatically generates interactive API documentation.

Swagger UI

```text
http://127.0.0.1:8000/docs
```

ReDoc

```text
http://127.0.0.1:8000/redoc
```

FastAPI automatically generates these OpenAPI docs based on your route definitions and Pydantic schemas. :contentReference[oaicite:0]{index=0}

---

## Future Improvements

- Authentication and Authorization
- Password hashing
- JWT authentication
- File upload for profile pictures
- Pagination
- Search and filtering
- Alembic database migrations
- Docker support
- Unit and Integration tests
- Role-based access control

---

## Learning Purpose

This project is part of my FastAPI learning journey. The focus is on understanding backend development concepts by building features step by step instead of using shortcuts or scaffolding tools.

Each feature was added incrementally to better understand how FastAPI, SQLAlchemy, and Pydantic work together.

---

## License

This project is open source and available under the MIT License.