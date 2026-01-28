# Python

## Detection signals
- `pyproject.toml`
- `requirements.txt`, `requirements-dev.txt`
- `Pipfile`, `poetry.lock`
- `setup.py`, `setup.cfg`
- `manage.py` (Django)

## Multi-module signals
- Multiple `pyproject.toml` in subdirs
- `packages/`, `apps/` directories
- Django-style `apps/` with `apps.py`

## Pre-generation sources
- `pyproject.toml` or `setup.py`
- `requirements*.txt`, `Pipfile`
- `tox.ini`, `pytest.ini`
- `manage.py`, `settings.py` (Django)

## Codebase scan patterns

### Source roots
- `src/`, `app/`, `packages/`, `tests/`

### Layer/folder patterns (record if present)
`api/`, `routers/`, `views/`, `services/`, `repositories/`, `models/`, `schemas/`, `utils/`, `config/`

### Pattern indicators

| Pattern | Detection Criteria | Skill Name |
|---------|-------------------|------------|
| FastAPI Router | `APIRouter`, `@router.get`, `@router.post` | fastapi-router |
| FastAPI Dependency | `Depends(`, `def get_*():` | fastapi-dependency |
| Django View | `View`, `APIView`, `def get(self, request)` | django-view |
| Django Model | `models.Model`, `class Meta:` | django-model |
| Django Serializer | `serializers.Serializer`, `ModelSerializer` | drf-serializer |
| Flask Route | `@app.route`, `Blueprint` | flask-route |
| Pydantic Model | `BaseModel`, `Field(`, `model_validator` | pydantic-model |
| SQLAlchemy Model | `Base`, `Column(`, `relationship(` | sqlalchemy-model |
| Alembic Migration | `alembic/versions/`, `op.create_table` | alembic-migration |
| Repository | `*Repository`, `class *Repository` | data-repository |
| Service | `*Service`, `class *Service` | service-layer |
| Celery Task | `@celery.task`, `@shared_task` | celery-task |
| CLI Command | `@click.command`, `typer.Typer` | cli-command |
| Unit Test | `pytest`, `def test_*():`, `unittest` | pytest-test |
| Fixture | `@pytest.fixture`, `conftest.py` | pytest-fixture |

## Mandatory output sections

Include if detected:
- **Routers/views**: API endpoints
- **Models/schemas**: data models (Pydantic, SQLAlchemy, Django)
- **Services**: business logic layer
- **Repositories**: data access layer
- **Migrations**: Alembic, Django migrations
- **Tasks**: Celery, background jobs

## Command sources
- `pyproject.toml` tool sections
- README/docs, CI
- Common: `python manage.py`, `pytest`, `uvicorn`, `flask run`
- Only include commands present in repo

## Key paths
- `src/`, `app/`
- `tests/`
- `alembic/`, `migrations/`
- `templates/`, `static/` (if web)
