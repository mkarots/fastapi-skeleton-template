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

# Docker commands
docker-build:
	docker build -t {{ project_name }}:latest .

docker-run:
	docker run -p 8000:8000 {{ project_name }}:latest

docker-compose-up:
	docker-compose up -d

docker-compose-down:
	docker-compose down

docker-compose-logs:
	docker-compose logs -f
