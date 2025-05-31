# Flask Todo App

A simple Flask-based todo application with PostgreSQL database, containerized with Docker.

## Features
- Add, edit, and delete todos
- PostgreSQL database
- Docker containerization
- Health checks
- Multi-stage Docker build

## Quick Start

### Using Docker Compose
```bash
docker-compose up -d
```

### Using Docker Hub Image
```bash
docker run -d -p 5000:5000 aashish29/todo-app:v1
```

## Files
- `app.py` - Flask application
- `Dockerfile` - Multi-stage Docker build
- `docker-compose.yml` - Docker Compose configuration
- `requirements.txt` - Python dependencies

## Endpoints
- `GET /` - Main todo interface
- `GET /health` - Health check endpoint
