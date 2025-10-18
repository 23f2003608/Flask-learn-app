
# Flask Learn App

A small, beginner-friendly Flask web application built to learn and demonstrate the basic building blocks of a Flask project: routing, templates, static assets, simple authentication flow, and a lightweight database. This repository contains the source code, templates, static files and an example SQLite database under `instance/`.

---

## Features

- Simple authentication pages: signup and login (with example flows)
- Modular project structure using a `website` package
- Jinja2 templates for layout and pages (`base.html`, `home.html`, `login.html`, `signup.html`)
- Static JS and CSS support in `static/` (example `script.js` included)
- Lightweight SQLite database stored in `instance/database.db` for local development

---

## Tech stack

- Python 3.8+ (should work on newer 3.x versions)
- Flask
- SQLite (for development)

See `requirements.txt` for the exact Python dependencies used by the project.

---

## Repository structure

Top-level layout (important files/folders):

- `main.py` — application entrypoint
- `requirements.txt` — Python dependencies
- `instance/` — contains `database.db` (local SQLite database)
- `website/` — Flask package with app factory and modules
	- `__init__.py`
	- `auth.py` — authentication routes and logic
	- `models.py` — data models or database helpers
	- `views.py` — other application routes
	- `templates/` — Jinja2 templates (`base.html`, `home.html`, `login.html`, `signup.html`)
	- `static/` — static assets (`script.js`, CSS, images)

This layout keeps UI, routes, and configuration organized and easy to extend.

---

## Quick start (macOS / zsh)

1. Clone the repository (if you haven't already):

```bash
git clone <your-repo-url>
cd Flask-learn-app
```

2. Create and activate a virtual environment (recommended):

```bash
python3 -m venv .venv
source .venv/bin/activate
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Ensure the `instance/` folder exists and the example database is present. If you don't have a database yet, the app may create one for you on first run or you can create it manually depending on how `models.py` is implemented.

5. Run the app:

```bash
# set the Flask entrypoint (macOS / zsh)
export FLASK_APP=main.py
export FLASK_ENV=development
flask run

# or run directly with python
python main.py
```

Open http://127.0.0.1:5000 in your browser.

---

## Routes (common pages)

These are the typical routes you will find in this repository. Your exact route names may vary slightly depending on how `views.py` and `auth.py` are implemented:

- `/` — Home page (`home.html`)
- `/login` — Login page (`login.html`)
- `/signup` — Signup / register page (`signup.html`)
- `/logout` — Logout action

Explore `website/views.py` and `website/auth.py` for the concrete implementations.

---

## Configuration & notes

- Secrets and production configuration should never be committed. Keep instance-specific or secret values in environment variables or an `instance/config.py` which is excluded from version control.
- For production, do not use the built-in Flask server. Use a production WSGI server like Gunicorn or uWSGI behind a reverse proxy.
- If you add migrations or change the model, consider using Flask-Migrate / Alembic for consistent database schema management.

Recommended `.gitignore` entries:

```
instance/
__pycache__/
.venv/
.env
*.pyc
```
---

## Acknowledgements

This project was created as a learning exercise to understand Flask fundamentals: routing, templates, and simple data persistence. Keep exploring Flask's official docs for more advanced patterns: https://flask.palletsprojects.com/

---

I
