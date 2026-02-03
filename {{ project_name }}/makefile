sync:
	uv sync --extra dev

run:
	uv run uvicorn {{ package_name }}.main:app --reload

test:
	uv run pytest -q

lint:
	uv run ruff check .

fmt:
	uv run ruff format .
