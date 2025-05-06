# 🛠️ ELT Pipeline with Airflow, PostgreSQL & dbt

This project implements an ELT (Extract, Load, Transform) pipeline using Python, Airflow, PostgreSQL, and dbt. It transfers data between PostgreSQL databases and performs data transformation using dbt. Docker is used to containerize services, and Airflow manages the workflow.

---

## 📦 Overview

1. **ELT Script (`elt_script.py`)**
   - Waits until the source PostgreSQL is ready.
   - Uses `pg_dump` to export the source database.
   - Loads the dumped SQL into the destination PostgreSQL using `psql`.

2. **Airflow DAG**
   - Task 1: Runs the ELT Python script.
   - Task 2: Executes `dbt run` with `--full-refresh` via Docker.

3. **dbt Macro**
   - Categorizes films based on user ratings.
   - Aggregates actor names per film.

---

## 🧰 Tech Stack

- Python 3
- PostgreSQL
- Airflow
- Docker
- dbt (Data Build Tool)
- Bash / Subprocess
- Jinja (for dbt macros)

---

## 🚀 Setup & Execution

### Prerequisites

- Docker + Docker Compose
- PostgreSQL (can be containerized)
- Airflow running (e.g., via Docker Compose)
- dbt installed (optional for local testing)
