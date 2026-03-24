# Django_Docker

# Django Library Application - Docker Setup

This guide explains how to build, run, and manage your Django Library application using Docker.

## Prerequisites

- Docker installed on your system ([Get Docker](https://docs.docker.com/get-docker/))
- Docker Compose (comes with Docker Desktop)
- Git

## Project Structure

```
├── Dockerfile              # Docker image configuration
├── docker-compose.yml      # Docker Compose configuration
├── .dockerignore           # Files to exclude from Docker image
└── library/                # Django application directory
    ├── manage.py
    ├── requirements.txt
    ├── db.sqlite3
    └── library/            # Project settings
```

## Building the Docker Image

Build the image from the Dockerfile:

```bash
docker build -t django-library:latest .
```

**Options:**
- `-t django-library:latest`: Tags the image with name and version
- `.`: Uses Dockerfile in current directory

## Running the Application

### Option 1: Using Docker Run (Direct)

Run a container from the image:

```bash
docker run -p 8000:8000 django-library:latest
```

**Options explained:**
- `-p 8000:8000`: Maps port 8000 from container to your machine
- `--name django_app`: Names the container (optional)
- `-e DEBUG=False`: Sets environment variables (optional)

Access the application at: http://localhost:8000

### Option 2: Using Docker Compose (Recommended)

Run the application with Docker Compose:

```bash
docker-compose up
```

**Useful commands:**
- `docker-compose up -d`: Run in detached mode (background)
- `docker-compose down`: Stop and remove containers
- `docker-compose logs`: View container logs
- `docker-compose logs -f`: Follow logs in real-time

Access the application at: http://localhost:8000