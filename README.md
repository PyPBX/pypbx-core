# PyPBX Core

**PyPBX Core** is the central backend engine for the [PyPBX Project](https://github.com/PyPBX) — an open-source, modular PBX platform built in Python.  
This repository contains the REST API, database models, business logic, and Asterisk integration components that power the platform.

---

## 🧩 What Is PyPBX Core?

PyPBX Core provides a modern, scalable backend for managing telephony infrastructure using **Asterisk**. It exposes a clean, documented REST API for managing:

- Extensions
- Dialplans
- Trunks
- Call queues
- IVRs
- Users & permissions
- Call recordings
- Configuration reloads

It's built using:

- ✅ **FastAPI** for API and async operations
- ✅ **SQLAlchemy** for DB abstraction
- ✅ **Jinja2** for Asterisk config generation
- ✅ **WebSockets** for live call events (via AMI)
- ✅ **Modular plugin system** for extensibility

---

## 🚀 Quick Start (Dev)

### Requirements
- Python 3.10+
- PostgreSQL (or MariaDB)
- Redis (optional, for task queue)
- Asterisk (running on localhost or via Docker)

### Setup

```bash
# Clone the repo
git clone https://github.com/PyPBX/pypbx-core.git
cd pypbx-core

# Create a virtual environment
python -m venv .venv
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Setup database
alembic upgrade head

# Run the dev server
uvicorn app.main:app --reload
