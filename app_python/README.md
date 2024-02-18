# Python Web Application

## Description

This is simple Python web application that displays the current time in Moscow.
To develop the app, I used the FastAPI framework, `datetime` to fetch the time and `pytz` to get the desired time zone.

## Start

### Installation process

1. Clone the repository: `git clone https://github.com/Alyona-art/S24-core-course-labs.git`
1. Change into the project directory: `cd app_python`
1. Install python packages `pip install -r requirements.txt`

### Usage

Run the application using the following command
```
uvicorn main:app
```

The application will be accessible at http://127.0.0.1:8000

## Unit Tests

Run the tests using the following command
```
unittest tests/time_tests.py
```

## Docker

### Build
```
docker build -t app-python .
```

### Pull

```
docker pull alyonaart/app-python:latest
```

### Run

```
docker run -d --name container_name -p 8000:8000 app-python
```

## CI workflow

![python-app workflow badge](https://github.com/Alyona-art/S24-core-course-labs/actions/workflows/app-python.yml/badge.svg) 

I used a GitHub Actions as a CI tool. The workflow is defined in `.github/workflows/python-app.yml`. It contains the following steps:

- Checkout
- Set up Python
- Install dependencies
- Cache dependencies
- Linting using `Flake8`
- Run unit tests
- Vulnerability check
- Login to DockerHub
- Build Docker image and push to DockerHub