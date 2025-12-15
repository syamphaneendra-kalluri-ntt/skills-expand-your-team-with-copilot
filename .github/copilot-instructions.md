# Copilot Instructions for Mergington High School Activities Website

## Project Overview

This is a web application for Mergington High School that allows students to view and sign up for extracurricular activities. The application consists of a Python/FastAPI backend with a simple HTML/CSS/JavaScript frontend.

## Development Environment

For detailed setup and development instructions, please refer to our [Development Guide](../docs/how-to-develop.md).

## Program Architecture

- **Backend**: Python with FastAPI framework
- **Frontend**: Static HTML/CSS/JavaScript served by FastAPI
- **Database**: MongoDB for storing activities and teacher accounts
- **Target Users**: Students and teachers (non-technical staff)

### Key Principles

- Keep the user experience simple for students and teachers
- Code should be maintainable without significant coding experience
- Use clear, organized directory structure (avoid single large files)
- Only use HTML, CSS, JavaScript, and Python - no other languages
- Do not create additional apps, services, or command line tools

## User Interaction

When communicating with school staff:
- Avoid technical jargon - use simple, clear explanations
- Remember that staff members are not technically oriented
- Focus on user-friendly solutions that work reliably

## Common Tasks

### Running the Application

```bash
# Install dependencies
pip install -r src/requirements.txt

# Start the server
python -m uvicorn src.app:app --host 0.0.0.0 --port 8000
```

### Adding a New Activity

Activities are defined in `src/backend/database.py` in the `initial_activities` dictionary. Each activity includes:
- Description
- Schedule (both human-readable and structured format)
- Maximum participants
- Current participants list

### API Structure

- `/activities` - Get all activities (supports filtering by day/time)
- `/activities/{name}/signup` - Sign up a student for an activity
- `/activities/{name}/unregister` - Remove a student from an activity
