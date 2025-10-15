# FastAPI - The Complete Course

Course and code created by: Eric Roby

## Overview

This repository contains a comprehensive FastAPI learning path from beginner to advanced concepts. The course is structured as a series of progressive projects that build upon each other, covering everything from basic API endpoints to full-stack web applications with authentication, database integration, and testing.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Projects Overview](#projects-overview)
- [Technologies Used](#technologies-used)
- [Running the Projects](#running-the-projects)
- [Database Configuration](#database-configuration)

## Prerequisites

- Python 3.8 or higher
- Basic understanding of Python programming
- Familiarity with REST APIs (helpful but not required)

## Installation

1. Clone this repository:
```bash
git clone <repository-url>
cd FAST_API_UDEMY_COURSE
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

## Project Structure

```
FAST_API_UDEMY_COURSE/
├── PythonRefresher/          # Python fundamentals review
├── Project 1/                # Basic FastAPI CRUD operations
├── Project 2/                # Advanced FastAPI with validation
├── Project 3/                # TodoApp with SQLite & Authentication
├── Project 3.5/              # TodoApp with Alembic migrations
├── Project 4/                # TodoApp with testing
├── Project 5/                # Full-stack TodoApp with templates
├── Database Scripts/         # MySQL & PostgreSQL setup scripts
└── requirements.txt          # Project dependencies
```

## Projects Overview

### Python Refresher
A comprehensive review of Python fundamentals including:
- Variables and data types
- Control structures (if/else, loops)
- Functions and imports
- Object-Oriented Programming (OOP)
- Collections (lists, dictionaries, sets, tuples)
- String formatting and user input

### Project 1: Books API (Basic CRUD)
**File:** [books.py](Project 1/books.py)

Introduction to FastAPI with a simple books management system:
- Basic GET, POST, PUT, DELETE endpoints
- Path parameters and query parameters
- In-memory data storage
- Basic filtering and searching

**Run:**
```bash
cd "Project 1"
uvicorn books:app --reload
```

### Project 2: Books API (Advanced)
**File:** [books2.py](Project 2/books2.py)

Enhanced version with data validation:
- Pydantic models for request validation
- Field validation with constraints
- HTTP status codes
- Error handling with HTTPException
- Path and query parameter validation
- API documentation with examples

**Run:**
```bash
cd "Project 2"
uvicorn books2:app --reload
```

### Project 3: Todo Application (Database Integration)
**Location:** [Project 3/TodoApp](Project 3/TodoApp)

Full-featured todo application with database:
- SQLite database with SQLAlchemy ORM
- User authentication with JWT tokens
- Password hashing with bcrypt
- Role-based access control (admin/user)
- Modular router structure
- CRUD operations for todos and users

**Key Files:**
- [main.py](Project 3/TodoApp/main.py) - Application entry point
- [database.py](Project 3/TodoApp/database.py) - Database configuration
- [models.py](Project 3/TodoApp/models.py) - SQLAlchemy models
- [routers/auth.py](Project 3/TodoApp/routers/auth.py) - Authentication endpoints
- [routers/todos.py](Project 3/TodoApp/routers/todos.py) - Todo CRUD operations
- [routers/users.py](Project 3/TodoApp/routers/users.py) - User management
- [routers/admin.py](Project 3/TodoApp/routers/admin.py) - Admin operations

**Run:**
```bash
cd "Project 3/TodoApp"
uvicorn main:app --reload
```

### Project 3.5: Todo Application (Database Migrations)
**Location:** [Project 3.5/TodoApp](Project 3.5/TodoApp)

Extends Project 3 with database migration capabilities:
- Alembic integration for database migrations
- Version control for database schema
- Migration scripts for schema changes
- Example: Adding phone_number column to users

**Run:**
```bash
cd "Project 3.5/TodoApp"
alembic upgrade head
uvicorn main:app --reload
```

### Project 4: Todo Application (Testing)
**Location:** [Project 4/TodoApp](Project 4/TodoApp)

Adds comprehensive testing suite:
- Unit tests with pytest
- Async test support with pytest-asyncio
- API endpoint testing with httpx
- Test coverage for authentication and CRUD operations
- Test database setup and teardown

**Run tests:**
```bash
cd "Project 4/TodoApp"
pytest
```

### Project 5: Full-Stack Todo Application
**Location:** [Project 5/TodoApp](Project 5/TodoApp)

Complete full-stack application with frontend:
- Jinja2 templates for server-side rendering
- Static file serving (CSS, JavaScript)
- HTML forms and user interface
- Session management
- Complete user authentication flow
- Responsive design

**Key Features:**
- Web-based user interface
- Login/Register pages
- Todo management dashboard
- User profile management
- Admin panel

**Run:**
```bash
cd "Project 5/TodoApp"
uvicorn main:app --reload
```

Visit: `http://localhost:8000`

## Technologies Used

### Core Framework
- **FastAPI** - Modern, fast web framework for building APIs

### Database & ORM
- **SQLAlchemy** - SQL toolkit and ORM
- **Alembic** - Database migration tool
- **SQLite** - Default database (development)
- **PostgreSQL** - Production database option
- **MySQL/PyMySQL** - Alternative database option
- **psycopg2-binary** - PostgreSQL adapter

### Authentication & Security
- **python-jose** - JWT token generation and validation
- **bcrypt** - Password hashing
- **passlib** - Password hashing library
- **cryptography** - Cryptographic recipes and primitives

### Testing
- **pytest** - Testing framework
- **pytest-asyncio** - Async test support
- **httpx** - HTTP client for testing

### Frontend & Files
- **Jinja2** - Template engine
- **aiofiles** - Async file operations
- **python-multipart** - Form data parsing

### Development
- **uvicorn** - ASGI server
- **numpy** - Numerical computing (if needed)

## Running the Projects

Each project can be run independently:

1. Navigate to the project directory
2. Start the FastAPI development server:
```bash
uvicorn <module>:app --reload
```

3. Access the interactive API documentation:
   - Swagger UI: `http://localhost:8000/docs`
   - ReDoc: `http://localhost:8000/redoc`

## Database Configuration

### SQLite (Default)
Projects 3-5 use SQLite by default. No additional setup required.

### PostgreSQL
To use PostgreSQL:

1. Run the setup script:
```bash
psql -U postgres -f "Database Scripts/PostgreSQLScript.sql"
```

2. Update `database.py`:
```python
SQLALCHEMY_DATABASE_URL = 'postgresql://user:password@localhost/TodoApplicationDatabase'
```

### MySQL
To use MySQL:

1. Run the setup script:
```bash
mysql -u root -p < "Database Scripts/MySQLScript.sql"
```

2. Update `database.py`:
```python
SQLALCHEMY_DATABASE_URL = 'mysql+pymysql://root:password@localhost:3306/TodoApplicationDatabase'
```

## API Documentation

Once the server is running, FastAPI automatically generates interactive API documentation:

- **Swagger UI**: Navigate to `/docs` for an interactive interface to test endpoints
- **ReDoc**: Navigate to `/redoc` for alternative documentation view

## Learning Path

Recommended order for working through the projects:

1. **Python Refresher** - Review Python fundamentals if needed
2. **Project 1** - Learn FastAPI basics and CRUD operations
3. **Project 2** - Master data validation and error handling
4. **Project 3** - Implement database integration and authentication
5. **Project 3.5** - Learn database migrations with Alembic
6. **Project 4** - Write tests for your API
7. **Project 5** - Build a complete full-stack application

## Key Concepts Covered

- RESTful API design
- Request/Response handling
- Data validation with Pydantic
- Database operations with SQLAlchemy
- JWT authentication
- Password hashing and security
- Database migrations
- API testing
- Template rendering
- Static file serving
- Error handling
- Status codes
- API documentation
- Modular application structure
- Dependency injection

## Contributing

This is a course repository. Feel free to experiment with the code and build upon these projects for your own learning.

## License

Course materials created by Eric Roby.

## Additional Resources

- [FastAPI Documentation](https://fastapi.tiangolo.com/)
- [SQLAlchemy Documentation](https://docs.sqlalchemy.org/)
- [Pydantic Documentation](https://docs.pydantic.dev/)
- [Alembic Documentation](https://alembic.sqlalchemy.org/)
