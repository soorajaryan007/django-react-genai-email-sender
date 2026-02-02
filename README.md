# Project Setup Guide

This guide will walk you through setting up and running the Django backend and React frontend for this application.

## Prerequisites

Before you begin, ensure you have the following installed:
- Python 3.8 or higher
- Node.js 16 or higher
- npm (comes with Node.js)
- pip (Python package installer)

## Project Structure

```
project-root/
├── backend_django/        # Django backend application
│   ├── manage.py
│   ├── requirements.txt
│   └── ...
├── frontend-react/        # React frontend application
│   ├── package.json
│   ├── src/
│   └── ...
└── README.md
```

## Setup Instructions

### 1. Backend Setup (Django)

#### Step 1: Activate Virtual Environment

First, create and activate a Python virtual environment to isolate project dependencies:

**On Linux/Mac:**
```bash
python3 -m venv venv
source venv/bin/activate
```

**On Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

#### Step 2: Navigate to Backend Directory

```bash
cd backend_django
```

#### Step 3: Install Python Dependencies

```bash
pip install -r requirements.txt
```

#### Step 4: Run Database Migrations (if needed)

```bash
python manage.py migrate
```

#### Step 5: Start the Django Development Server

```bash
python manage.py runserver
```

The Django backend should now be running at `http://localhost:8000`

---

### 2. Frontend Setup (React)

Open a new terminal window/tab (keep the Django server running in the first terminal).

#### Step 1: Navigate to Frontend Directory

```bash
cd frontend-react
```

#### Step 2: Install Node Dependencies

```bash
npm install
```

#### Step 3: Install Lucide React Icons

```bash
npm install lucide-react
```

#### Step 4: Start the React Development Server

```bash
npm start
```

The React frontend should now be running at `http://localhost:3000` and will automatically open in your browser.

---

## Quick Start Commands

For convenience, here's the full sequence of commands:

### Terminal 1 (Backend):
```bash
# Activate virtual environment
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Go to backend directory
cd backend_django

# Install requirements
pip install -r requirements.txt

# Run Django server
python manage.py runserver
```

### Terminal 2 (Frontend):
```bash
# Go to frontend directory
cd frontend-react

# Install dependencies
npm install

# Install lucide-react
npm install lucide-react

# Start React app
npm start
```

## Common Issues and Troubleshooting

### Virtual Environment Issues
- **Issue:** `venv` command not found
- **Solution:** Try `python3 -m venv venv` or ensure Python is properly installed

### Port Already in Use
- **Django (8000):** Use `python manage.py runserver 8001` to run on a different port
- **React (3000):** React will automatically suggest port 3001 if 3000 is busy

### Module Not Found Errors
- **Backend:** Ensure virtual environment is activated and all requirements are installed
- **Frontend:** Delete `node_modules` and `package-lock.json`, then run `npm install` again

### CORS Issues
If the frontend can't communicate with the backend, you may need to configure CORS in Django:
1. Install `django-cors-headers`: `pip install django-cors-headers`
2. Add it to `INSTALLED_APPS` in settings.py
3. Add `corsheaders.middleware.CorsMiddleware` to `MIDDLEWARE`
4. Add `CORS_ALLOWED_ORIGINS = ['http://localhost:3000']` to settings.py

## Development Workflow

1. Always activate the virtual environment before working on the backend
2. Keep both servers running during development
3. Changes to React code will hot-reload automatically
4. Django will auto-reload when you save Python files
5. Remember to commit both `requirements.txt` and `package.json` when you add new dependencies

## Stopping the Servers

- **Django:** Press `Ctrl+C` in the terminal running Django
- **React:** Press `Ctrl+C` in the terminal running React
- **Deactivate virtual environment:** Type `deactivate` in the terminal

## Additional Resources

- [Django Documentation](https://docs.djangoproject.com/)
- [React Documentation](https://react.dev/)
- [Lucide React Icons](https://lucide.dev/guide/packages/lucide-react)

## Next Steps

- Configure environment variables for sensitive data
- Set up a `.env` file for both frontend and backend
- Configure a production deployment strategy
- Add API documentation
- Set up testing frameworks
---


