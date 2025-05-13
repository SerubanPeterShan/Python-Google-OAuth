# Flask Web Application with Google OAuth and Local Authentication

This is a Python web application built with Flask that supports both local authentication and Google Sign-In using OAuth 2.0.

## Features
- User registration and login with email and password
- Sign in with Google (OAuth 2.0)
- User session management (login/logout)
- Dashboard for authenticated users

## Prerequisites
- Python 3.8 or higher
- [Poetry](https://python-poetry.org/docs/#installation) for dependency management
- Google Cloud project with OAuth 2.0 credentials

## Setup Instructions

### 1. Clone the repository
```bash
git clone <your-repo-url>
cd <your-repo-directory>
```

### 2. Install dependencies with Poetry
```bash
poetry install
```

### 3. Set up environment variables
Create a `.env` file in the project root with the following content:
```env
GOOGLE_CLIENT_ID=your-google-client-id.apps.googleusercontent.com
GOOGLE_CLIENT_SECRET=your-google-client-secret
GOOGLE_REDIRECT_URI=http://localhost:5000/google/callback
GOOGLE_PROJECT_ID=your-google-project-id
```
- Replace the values with your credentials from the [Google Cloud Console](https://console.developers.google.com/apis/credentials).
- Make sure the redirect URI matches what you set in the Google Console.

### 4. Initialize the database (first run only)
```bash
poetry run python app.py
```
This will create the `users.db` SQLite database if it does not exist.

### 5. Run the application
```bash
poetry shell
python app.py
```
The application will be available at [http://localhost:5000](http://localhost:5000)

## Usage
- Register a new account or use the "Sign in with Google" button on the login page.
- After login, you will be redirected to the dashboard.
- Use the logout button to end your session.

## Troubleshooting
- **OAuth errors:** Ensure your `.env` values match the Google Console credentials and the redirect URI is correct.
- **Dependencies:** Always use `poetry install` to manage dependencies.
- **Database issues:** Delete `users.db` to reset users (for development/testing only).

## License
This project is for educational purposes. 