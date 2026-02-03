# FastAPI Skeleton Template

A Copier template for quickly scaffolding FastAPI applications with a clean, production-ready structure.

## What This Template Provides

This template generates a FastAPI project skeleton with:

- **FastAPI** application with dependency injection pattern
- **Optional SQLAlchemy** integration for database operations
- **Optional OpenTelemetry** support for observability
- **Structured logging** configuration
- **Service layer** architecture with dependency injection
- **API routes** with health check endpoint
- **Pydantic** models for request/response validation
- **Development tools**: pytest, ruff for testing and linting

## Prerequisites

- Python 3.11+
- [Copier](https://copier.readthedocs.io/) installed (`pip install copier` or `pipx install copier`)
- [uv](https://github.com/astral-sh/uv) (recommended) or pip for package management

## Usage

1. **Copy the template to create a new project:**
   ```bash
   copier copy gh:mkarots/fastapi-skeleton-template my-new-service
   ```

2. **Navigate to the new project directory:**
   ```bash
   cd my-new-service
   ```

   **Note:** If files are created in a `template/` subdirectory, move them to the root:
   ```bash
   cd my-new-service
   mv template/* . && mv template/.* . 2>/dev/null || true
   rmdir template
   ```

3. **Set up a virtual environment and install dependencies:**
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   pip install -e .
   ```

4. **Run the development server:**
   ```bash
   uvicorn <package_name>.main:app --reload
   ```
   (Replace `<package_name>` with your chosen package name, default is `app`)

The application will be available at `http://localhost:8000` with API documentation at `http://localhost:8000/docs`.

## Template Configuration

During the `copier copy` process, you'll be prompted for:

- **project_name**: Name of your project folder (e.g., `my-api`)
- **package_name**: Python package name (default: `app`)
- **service_name**: Service name for logging/telemetry (default: same as project_name)
- **use_sqlalchemy**: Include SQLAlchemy database integration? (default: `true`)
- **use_telemetry**: Include OpenTelemetry observability? (default: `true`)

## Project Structure

```
my-new-service/
├── app/
│   ├── __init__.py
│   ├── main.py              # FastAPI app entry point
│   ├── composition.py        # Dependency injection container
│   ├── config.py            # Configuration management
│   ├── api/
│   │   └── routes.py        # API route definitions
│   ├── service/
│   │   └── handlers.py      # Business logic handlers
│   └── infra/
│       ├── db.py            # Database setup (if enabled)
│       ├── logging.py       # Logging configuration
│       ├── middleware.py    # Request/response middleware
│       └── telemetry.py     # Telemetry setup (if enabled)
├── tests/                   # Test files
│   ├── test_api.py
│   └── test_service.py
├── .env.example             # Environment variables template
├── .gitignore               # Git ignore rules
├── makefile                 # Common development commands
├── pyproject.toml           # Project dependencies and config
└── README.md                # Generated project README
```

## License

[Add your license here]
