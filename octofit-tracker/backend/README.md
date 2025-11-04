OctoFit Tracker backend — quick start

This folder contains a minimal Django project used as the backend for the OctoFit Tracker app.

Prerequisites
- Python 3.10+ (the venv here was created with python3)
- A working virtual environment located at `octofit-tracker/backend/venv` (created already)

Activate the virtualenv (bash):

```bash
source /workspaces/build-applications-w-copilot-agent-mode/octofit-tracker/backend/venv/bin/activate
```

Install dependencies (if you change `requirements.txt`):

```bash
pip install -r /workspaces/build-applications-w-copilot-agent-mode/octofit-tracker/backend/requirements.txt
```

Run initial migrations and start the dev server:

```bash
python /workspaces/build-applications-w-copilot-agent-mode/octofit-tracker/backend/manage.py migrate
python /workspaces/build-applications-w-copilot-agent-mode/octofit-tracker/backend/manage.py createsuperuser  # optional
python /workspaces/build-applications-w-copilot-agent-mode/octofit-tracker/backend/manage.py runserver 0.0.0.0:8000
```

Notes
- The app uses MongoDB via `djongo`/`pymongo` per project instructions. Make sure a MongoDB service is available if you plan to configure production settings.
- Ports: the dev server uses port 8000 by default (allowed by project instructions).

Next steps
1. Add an app (e.g., `activities`) with `python manage.py startapp activities`.
2. Wire the REST API with `djangorestframework` and authentication (`django-allauth`, `dj-rest-auth`).
3. Add CI, tests, and Docker if desired.
