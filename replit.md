# Image Hoster

A simple Flask-based image hosting web application.

## Overview

Users can upload images via a web form, which are stored in the `uploads/` directory and served back via a generated URL.

## Project Structure

- `main.py` - Flask application entry point
- `templates/index.html` - Upload form HTML template
- `uploads/` - Directory where uploaded images are stored

## Running the App

The app runs on port 5000:

```
python main.py
```

## Dependencies

- Flask
- Werkzeug
- Gunicorn (for production)

## Deployment

Configured for VM deployment using Gunicorn:

```
gunicorn --bind=0.0.0.0:5000 --reuse-port main:app
```

VM target is used because the app stores uploaded files on disk (persistent state).
