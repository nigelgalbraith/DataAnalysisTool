# DataAnalysisTool

DataAnalysisTool is a Dockerized Flask API for managing, inspecting, and interacting with structured relational datasets.

It provides database introspection, table-level operations, structured data entry, configuration management, and summary reporting through a modular API architecture.

⚠ This project is currently under active development.

---

## Overview

DataAnalysisTool is built around:

- Flask-based REST API
- PostgreSQL backend (psycopg2)
- Modular route blueprints
- Docker + Docker Compose orchestration
- Nginx configuration
- Structured import utilities (CSV → SQL)

It’s a structured API for inspecting and working with relational databases.

---

## Core Capabilities

### Database Introspection

- List databases
- Inspect tables
- Inspect columns
- View foreign key relationships
- Retrieve metadata

---

### Data Entry & Management

- Insert structured records
- Validate inputs
- Enforce foreign key constraints
- Handle constraint violations gracefully

---

### Summary & Reporting

- Dataset summaries
- Structured aggregate views
- Database-level overview endpoints

---

### Configuration Management

- Load and manage configuration data
- Structured config storage
- Config validation modules

---

### Backup & Startup Tasks

- Startup backup execution
- Conditional startup task execution
- Modular backup logic

---

### CSV → SQL Conversion

Utilities included for:

- Converting CSV files into SQL
- Structured import preparation
- Sample import configuration

Located in:

```
imports/
```

---

## Architecture

The system is structured as:

```
Docker Environment
        ↓
Flask Application (api/app.py)
        ↓
Blueprint Routes
        ↓
Service Modules
        ↓
PostgreSQL Database
```

---

## API Structure

Blueprint-based modular routing:

- `routes/databases.py`
- `routes/tables.py`
- `routes/columns.py`
- `routes/foreign_keys.py`
- `routes/summary.py`
- `routes/data_entry.py`
- `routes/configs.py`
- `routes/introspection.py`
- `routes/docs.py`
- `routes/health.py`
- `routes/pages.py`

Supporting modules:

- `modules/db.py`
- `modules/validators.py`
- `modules/sql_utils.py`
- `modules/summary_service.py`
- `modules/backups.py`
- `modules/config_store.py`
- `modules/responses.py`

---

## Error Handling

The API includes structured PostgreSQL error mapping:

- Unique constraint violations → 409
- Foreign key violations → 409
- NOT NULL violations → 400
- CHECK violations → 400

Unhandled errors are safely wrapped in structured JSON responses.

---

## Deployment

The project includes:

- `docker-compose.yml`
- `api.Dockerfile`
- `nginx.conf`
- `manage.sh` (interactive Docker manager)

---

## Running the Application

Using Docker Compose directly:

```bash
docker compose up -d
```

Or use the interactive manager:

```bash
./manage.sh
```

Options include:

- Start containers
- Stop containers
- Restart
- Rebuild (no cache)
- View logs
- Show status

---

## Project Structure

```
DataAnalysisTool/
│
├── api/
│   ├── app.py
│   ├── routes/
│   ├── modules/
|
├── site/
|   ├── index.html
|   ├── src/
|   ├── style/
|
├── imports/
│   ├── config/
│   ├── csv/
│   ├── sql/
│
├── storage/
│   ├── backups/
│   ├── config/
│
├── docker-compose.yml
├── api.Dockerfile
├── nginx.conf
├── manage.sh
```

---

## Design Principles

DataAnalysisTool is built around:

- Modular route separation
- Clear service boundaries
- Explicit error handling
- Structured database interaction
- Dockerized reproducibility
- Configuration-driven imports

---

## Current Development Focus

- Refining modular service layers
- Expanding summary endpoints
- Strengthening validation logic
- Improving structured import tooling
- Stabilizing configuration handling

---


## License

MIT License.

Anyone is free to use, modify, distribute, or improve this code.
