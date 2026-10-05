# Async SQLAlchemy and MySQL Example

Python database reference project using repository and unit-of-work patterns.

## How it works

An async SQLAlchemy engine connects to MySQL through asyncmy. The car repository performs CRUD queries; the unit of work manages sessions and transactions. An initialisation module creates tables and imports `data/cars.csv`, and a demo script exercises CRUD operations.

## Usage

Requires Python 3.13 or later and an existing MySQL database. Configure `DB_HOST`, `DB_PORT`, `DB_USER`, `DB_PASS` and `DB_NAME` in the environment or a local `.env` file.

From the repository root, inside your Python environment:

```sh
python -m pip install -e ".[dev]"
python -m db_example.db.init_db
python -m db_example.scripts.demo_crud
```

## Notes

Use the editable package install above; `requirements.txt` contains an author-local filesystem path. The pytest suite requires a dedicated test database because its fixtures recreate tables. This is a database module and command-line demonstration, not a web API.
