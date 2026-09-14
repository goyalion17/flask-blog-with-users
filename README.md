# Flask Blog with Users

A student/learning project: a multi-user blogging platform built with Flask. Registered users can read posts and leave comments, while the first registered user is granted admin rights to create, edit, and delete posts.

This project was built while following an online Python/Flask course as a hands-on exercise in authentication, authorization, and relational database design.

## Features

- User registration and login with hashed & salted passwords
- Session-based authentication (remembers who's logged in)
- Admin-only post creation, editing, and deletion (first registered user = admin)
- Rich text editing for posts and comments (CKEditor)
- Comments on blog posts, restricted to logged-in users
- Relational data model: `User` ⇄ `BlogPost` ⇄ `Comment` (one-to-many relationships with foreign keys)
- Flash messages for user feedback (duplicate email/title, wrong credentials, etc.)
- Responsive Bootstrap 5 UI

## Tech stack

**Backend**
- [Python 3](https://www.python.org/)
- [Flask](https://flask.palletsprojects.com/) — web framework
- [Flask-SQLAlchemy](https://flask-sqlalchemy.palletsprojects.com/) — ORM (SQLAlchemy 2.0 style)
- [Flask-Login](https://flask-login.readthedocs.io/) — user session management
- [Flask-WTF](https://flask-wtf.readthedocs.io/) + [WTForms](https://wtforms.readthedocs.io/) — forms and CSRF protection
- [email-validator](https://github.com/JoshData/python-email-validator) — email field validation
- [Werkzeug](https://werkzeug.palletsprojects.com/) — password hashing (`pbkdf2:sha256`)
- [Bootstrap-Flask](https://bootstrap-flask.readthedocs.io/) — Jinja macros for Bootstrap 5 forms
- [Flask-CKEditor](https://flask-ckeditor.readthedocs.io/) — rich text editor integration

**Database**
- [SQLite](https://www.sqlite.org/) — local file-based relational database

**Frontend**
- [Bootstrap 5](https://getbootstrap.com/)
- [CKEditor 4 (4.25.2-lts)](https://ckeditor.com/ckeditor-4/) — loaded from CDN
- [Jinja2](https://jinja.palletsprojects.com/) — templating engine
- [Font Awesome](https://fontawesome.com/) — icons
- [Google Fonts](https://fonts.google.com/) (Lora, Open Sans)

**Tooling**
- `venv` — Python virtual environment
- `pip` — dependency management
- [DB Browser for SQLite](https://sqlitebrowser.org/) — recommended for inspecting the local database

## Getting started

1. Clone the repository and move into the project folder:
   ```bash
   git clone https://github.com/goyalion17/flask-blog-with-users.git
   cd flask-blog-with-users
   ```

2. Create and activate a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate   # Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Run the app:
   ```bash
   python main.py
   ```

5. Open [http://127.0.0.1:5002](http://127.0.0.1:5002) in your browser.

The database (`instance/posts.db`) is created automatically on first run. **The first user you register becomes the site admin** and is the only one who can create, edit, or delete posts.

## Project structure

```
├── main.py              # Flask app, routes, database models
├── forms.py             # WTForms form definitions
├── requirements.txt     # Python dependencies
├── templates/           # Jinja2 HTML templates
├── static/               # CSS, JS, images
└── instance/             # SQLite database (auto-created, git-ignored)
```
