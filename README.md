# Developing CI/CD Workflow with GitHub Actions

This repository contains the code for setting up a CI/CD pipeline using GitHub Actions.
This is a portfolio project and it is not intended for commercial use. 

## Scripts

### 1. app.py
A Python script that creates a microservice for serving mascot data. It uses the Flask framework. The service loads mascot data from a JSON file and provides two GET endpoints for fetching the list of all mascots and a specific mascot based on its GUID.

### 2. pipeline.yml
A GitHub Actions workflow that sets up a CI/CD pipeline. The pipeline performs the following steps in sequence:

- Lints the Python code
- Runs unit tests
- Builds a Docker image
- Pushes the image to Google Cloud Platform's Image Registry
- Runs unit tests in the Docker container
- Deploys the Docker image to Cloud Run
- Tests the deployment

### 3. Dockerfile
A Dockerfile that sets up a Docker image with the Flask application. It uses a Python 3.6 base image, sets the working directory, installs necessary Python packages, exposes port 8080, sets `python` as the entrypoint, and runs `/app/app.py` when a container starts from this image.

## Dependencies
- Python
- Flask
- Docker
- Google Cloud Platform (GCP)
- GitHub Actions

Please ensure to replace all the secrets and environment variables in the pipeline.yml with your own values.

## Data
The `data.json` file in the repository contains data about different mascots and their related information including the mascot's unique identifier (GUID), the name of the school, the mascot's name, the school's nickname, the location of the school, and the latitude-longitude coordinates of the school. Some of the schools in the data include Iowa State University, Baylor University, University of Kansas, Kansas State University, University of Oklahoma, Oklahoma State University, and more.

