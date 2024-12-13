# Flask Docker App

This project demonstrates how to containerize a simple Flask application using Docker Compose including Docker volumes.

## Dependencies

- Flask (listed in `requirements.txt`)

## How it Works

1. **Dockerfile**: Defines the environment for the Flask app, using the `python:3.10-slim` image as the base. It installs dependencies from `requirements.txt` and runs the app.
2. **docker-compose.yml**: Defines the `flask-app` service with the `mintah/flask-app:1.0` image tag. It exposes port `8080` and mounts a local directory (`./files_directory`) to `/app/data` in the container. The app runs in a `dev-network` bridge network.

## How to Run

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd <repository-directory>

2. **Build Docker Compose**:
    ```bash
   sudo docker-compose build

3. **Check Built Images**:
    ```bash
   sudo docker images ls

4. **Start Docker Compose**:
    To start run your built docker images specified in the docker compose file, you run:

    ```bash
   sudo docker-compose up

5. **Push Docker Image to Docker Hub**:
    To push your tagged image i.e `image: <username>/flask-app:1.0` to github, you enter the command
    ```bash
   sudo docker-compose push

6. **Shutdown running containers by Docker Compose**:
    Once you're done running your services you can terminate them by running this command
    ```bash
   sudo docker-compose down