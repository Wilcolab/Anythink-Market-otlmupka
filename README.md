# Python Server

This project contains a FastAPI server implemented in Python. It provides two routes for managing a task list.

## Project Structure

The project has the following files and directories:

- `python-server/src/main.py`: This file contains the implementation of the FastAPI server with two routes. It handles adding a task to a list and retrieving the list.

- `python-server/src/__init__.py`: This file is an empty file that marks the `src` directory as a Python package.

- `python-server/requirements.txt`: This file lists the dependencies required for the FastAPI server and other dependencies.

- `python-server/Dockerfile`: This file is used to build a Docker image for the FastAPI server. It specifies the base image, copies the source code into the image, installs the dependencies, and sets the command to run the server.

- `docker-compose.yml`: This file is used to define and run multi-container Docker applications. It specifies the services to run, their configurations, and any dependencies between them.

## Services

### Python FastAPI Server (Port 8000)
- `GET /` - Returns "Hello World"
- `POST /tasks` - Add a new task
- `GET /tasks` - Get all tasks

### Node.js Express Server (Port 8001)
- `GET /` - Returns "Hello World"
- `POST /tasks` - Add a new task
- `GET /tasks` - Get all tasks

## Getting Started

1. Build and start both servers:
```bash
docker compose up
```

## API Routes

The FastAPI server provides the following API routes:

- `POST /tasks`: Adds a task to the task list. The request body should contain the task details.

- `GET /tasks`: Retrieves the task list.

## Migration

The project includes two identical APIs implemented in different technologies to demonstrate migration capabilities:

### Python to Node.js Migration
1. Data Structure:
   - Both servers use an in-memory array to store tasks
   - Task format is identical: simple strings in an array

2. API Compatibility:
   - Identical endpoints and response formats
   - Same HTTP methods (GET/POST)
   - Matching JSON schemas

### Testing Migration
To verify both servers work identically:

```bash
# Test Python Server (8000)
curl -X POST http://localhost:8000/tasks \
  -H "Content-Type: application/json" \
  -d '{"text":"New task"}'

curl http://localhost:8000/tasks

# Test Node.js Server (8001)
curl -X POST http://localhost:8001/tasks \
  -H "Content-Type: application/json" \
  -d '{"text":"New task"}'

curl http://localhost:8001/tasks
