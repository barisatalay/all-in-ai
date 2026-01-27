# Python

## Detection signals
- `pyproject.toml`
- `requirements.txt`, `requirements-dev.txt`, `Pipfile`, `poetry.lock`
- `tox.ini`, `pytest.ini`
- `manage.py`
- `setup.py`, `setup.cfg`
- `settings.py`, `urls.py` (Django)

## Multi-module signals
- Multiple `pyproject.toml`/`setup.py`/`setup.cfg` in subdirs
- `packages/` or `apps/` each with its own package config
- Django-style `apps/` with multiple `apps.py` (if present)

## Before generating, analyze these sources
- `pyproject.toml` or `setup.py` / `setup.cfg`
- `requirements*.txt`, `Pipfile`, `poetry.lock`
- `tox.ini`, `pytest.ini`
- `manage.py`, `settings.py`, `urls.py` (if Django)
- Package roots under `src/`, `app/`, `packages/` (if present)

## Codebase scan (Python-specific)
- Source roots: `src/`, `app/`, `packages/`, `tests/`
- Folder patterns (record only if present):
  `api`, `routers`, `views`, `services`, `repositories`,
  `models`, `schemas`, `utils`, `config`
- Django structure (record only if present):
  `apps.py`, `models.py`, `views.py`, `urls.py`, `migrations/`, `settings.py`
- FastAPI/Flask markers (record only if present):
  `FastAPI()`, `APIRouter`, `@app.get`, `@router.post`,
  `Flask(__name__)`, `Blueprint`
- Type model usage (record only if present):
  `pydantic.BaseModel`, `TypedDict`, `dataclass`

## Mandatory output (Python module CLAUDE.md)
Include these if detected (list actual names found):
- **Routers/views**: list API router or view files
- **Services**: list service modules
- **Models/schemas**: list data models (Pydantic, SQLAlchemy, Django)
- **Repositories**: list repository or DAO modules
- **Migrations**: mention migrations dir
- **Middleware**: list middleware classes
- **Django apps**: list installed apps (if Django)

## Command sources
- `pyproject.toml` tool sections
- README/docs or CI
- Repo scripts invoking Python tools
- `python manage.py`, `pytest`, `tox` usage in docs/scripts
- Only include commands present in repo

## Key paths to mention (only if present)
- `src/`, `app/`, `scripts/`
- `templates/`, `static/`
- `tests/`
