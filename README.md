# Insight-Backend-Test

Backend Test for Insait

# Flask App Documentation

This README provides an overview of the Flask app, including how to build, run, and manage the application using Docker, as well as database migrations. Additionally, it provides details on how to use the associated `Makefile` for ease of development.

## Requirements

Before running the Flask app in Docker, make sure you have the following installed on your machine:

- Docker
- Docker Compose

If you don't have `make` installed, you can still execute the individual Docker commands as described below.

## Local Setup

To set up and run the Flask app in Docker, follow the steps below.

### Clone the Repository

```bash
git clone https://github.com/Ade-Pyaar/Insight-Backend-Test
cd Insight-Backend-Test
```

### Environment Configuration

Create a .env file in the root directory of the project. A sample is provided in the `.env.example` with the required keys

### Using Makefile Commands

The Makefile simplifies the process of interacting with Docker Compose and Alembic for managing your Flask app. Below are the available commands you can run with make. If you do not have make installed, you can always copy the Docker commands from the descriptions and run them manually.

1. Build Docker Image
   This command builds the Flask app Docker image.

```bash
make build
```

2. Run Docker Image
   This command runs the Flask app Docker image.

```bash
make run
```

3. Build and run the Docker Image
   This command build the docker image and then runs it after the build has been completed

```bash
make build-run
```

4. Make migrations
   After the container has been built (or when it is running), the command below can be executed to create database tables using Alembic

```bash
make migrate
```

5. Run Test
   To run the test using pytest, run the below command

```bash
make test
```

6. Shutdown the container
   To stop the container, run the below command

```bash
make down
```

### Manual Docker Commands

If you don't have make installed, you can open up the make file, copy out the docker command under the make command you want to execute and run it directly in your terminal.

### Making requests

Once the docker image is running, you can access the `/ask`anedpoint by making a request to `http://localhost:8000/ask`
A sample payload is show below

```json
{
  "question": "In 250 characters, what is Flask in Python?"
}
```

A sample response is shown below

```json
{
  "answer": "Django is a high-level Python web framework that encourages rapid development and clean, pragmatic design. It promotes the use of the Model-View-Template (MVT) architecture, providing built-in features like an admin panel, ORM, and security tools for developers.",
  "created_at": "Fri, 20 Dec 2024 16:00:45 GMT",
  "id": 4,
  "question": "In 250 characters, what is Django?"
}
```
