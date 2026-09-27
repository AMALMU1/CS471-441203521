# Book Library — Django Project

CS471 course project. Django application that hosts two service modules,
`bookmodule` and `usermodule`. This folder is the project ROOT (it contains
`manage.py`).

## Lab 2 — Django framework setup and Git

### Structure

```
book-library/                 <- ROOT (contains manage.py)
├── .gitignore
├── manage.py
├── db.sqlite3
├── libraryproject/           <- project package
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│   └── asgi.py
└── apps/
    ├── static/               <- project static files
    ├── templates/            <- project templates
    ├── bookmodule/           <- service 1
    └── usermodule/           <- service 2
```

### Running it

Create the virtual environment **outside** this repository:

```bash
python -m venv djangoenv
cd djangoenv
Scripts\activate          # Windows
source bin/activate       # macOS / Linux
pip install django
```

Then, from this folder:

```bash
python manage.py migrate
python manage.py runserver
```

Open http://127.0.0.1:8000/

### Configuration notes

- Both modules are registered in `libraryproject/settings.py`:
  `INSTALLED_APPS` contains `apps.bookmodule` and `apps.usermodule`.
- Each module declares its dotted path in `apps.py`
  (`name = 'apps.bookmodule'`, `name = 'apps.usermodule'`).
- Templates resolve from `apps/templates`, static files from `apps/static`.
- `migrations/` folders are intentionally untracked, per the lab handout's
  `.gitignore` list.
