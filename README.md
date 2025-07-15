# Flaskr - A Flask Blog Application

Flaskr is a simple blog application built with Flask. It allows users to register, log in, create, edit, and delete blog posts.

## Features

- **User Authentication**
  - User registration with username and password
  - Secure password hashing
  - Login/logout functionality
  - Protected routes requiring authentication

- **Blog Management**
  - View all posts on the homepage
  - Create new blog posts
  - Edit your own posts
  - Delete your own posts
  - Posts display author and creation timestamp

## Installation

### Prerequisites
- Python 3.11 or higher
- Poetry (for dependency management)

### Setup

1. Clone the repository:
   ```
   git clone <repository-url>
   cd flask-tutorial
   ```

2. Install dependencies using Poetry:
   ```
   poetry install
   ```

3. Initialize the database:
   ```
   poetry run flask --app flaskr init-db
   ```

## Usage

### Development Server

Run the development server:
```
poetry run python main.py
```

The application will be available at http://127.0.0.1:5000/

### Production Deployment

For production deployment, you can use Waitress (included in dependencies):
```
poetry run waitress-serve --call 'flaskr:create_app'
```

## Project Structure

- **flaskr/**: Main application package
  - **__init__.py**: Application factory and configuration
  - **db.py**: Database connection and initialization
  - **schema.sql**: SQL schema for the database
  - **auth.py**: Authentication routes and functionality
  - **blog.py**: Blog routes and functionality
  - **static/**: Static files (CSS, JavaScript)
  - **templates/**: Jinja2 templates for rendering pages
    - **auth/**: Authentication templates
    - **blog/**: Blog templates
    - **base.html**: Base template with common layout

- **test/**: Test package
  - **test_factory.py**: Tests for the application factory
  - **test_db.py**: Tests for database functionality

- **main.py**: Entry point for running the application
- **pyproject.toml**: Project metadata and dependencies

## Testing

Run tests with pytest:
```
poetry run pytest
```

For test coverage:
```
poetry run coverage run -m pytest
poetry run coverage report
```

## License

See the LICENSE file for details.
