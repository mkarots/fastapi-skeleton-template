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
- [uv](https://github.com/astral-sh/uv) (recommended) for package management

## Usage

1. **Copy the template to create a new project:**
   ```bash
   copier copy gh:mkarots/fastapi-skeleton-template my-new-service
   ```

2. **Navigate to the new project directory:**
   ```bash
   cd my-new-service
   ```

3. **Install dependencies:**
   ```bash
   make sync
   # or
   uv sync --extra dev
   ```

4. **Run the development server:**
   ```bash
   make run
   # or
   uvicorn app.main:app --reload
   ```
   (Replace `app` with your chosen package name if different)

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
├── app/                      # Main package (name customizable)
│   ├── __init__.py
│   ├── main.py              # FastAPI app entry point
│   ├── composition.py        # Dependency injection container
│   ├── config.py            # Configuration management
│   ├── api/
│   │   ├── __init__.py
│   │   └── routes.py        # API route definitions
│   ├── service/
│   │   ├── __init__.py
│   │   └── handlers.py      # Business logic handlers
│   └── infra/
│       ├── __init__.py
│       ├── db.py            # Database setup (if enabled)
│       ├── logging.py       # Logging configuration
│       ├── middleware.py    # Request/response middleware
│       └── telemetry.py     # Telemetry setup (if enabled)
├── tests/                   # Test files
│   ├── __init__.py
│   ├── test_api.py
│   └── test_service.py
├── .gitignore               # Git ignore rules
├── makefile                 # Common development commands
├── pyproject.toml           # Project dependencies and config
└── README.md                # Generated project README
```

## Quick Start After Generation

After running `copier copy`, the template automatically:
1. Initializes a git repository
2. Attempts to install dependencies (if `uv` is available)
3. Provides next steps

Then you can:
```bash
cd my-new-service
make sync    # Install dependencies
make run     # Start development server
make test    # Run tests
make lint    # Check code quality
make fmt     # Format code
```

## License

[Add your license here]
