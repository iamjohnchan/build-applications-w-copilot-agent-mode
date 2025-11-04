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

Run initial migrations:

```bash
python /workspaces/build-applications-w-copilot-agent-mode/octofit-tracker/backend/manage.py migrate
```

To run the Django app, use the VS Code Run/Debug configuration:

1. Open the Run and Debug panel in VS Code (Ctrl+Shift+D)
2. Select "Launch Django Backend" from the dropdown
3. Click the green Run button (or press F5)

This will start the Django development server using the settings in `.vscode/launch.json`.

Notes
- The app uses MongoDB via `djongo`/`pymongo` per project instructions. Make sure a MongoDB service is available if you plan to configure production settings.
- Ports: the dev server uses port 8000 by default (allowed by project instructions).

Next steps
1. Add an app (e.g., `activities`) with `python manage.py startapp activities`.
2. Wire the REST API with `djangorestframework` and authentication (`django-allauth`, `dj-rest-auth`).
3. Add CI, tests, and Docker if desired.
