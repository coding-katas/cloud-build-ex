# Project "cloud build"

This is a Python web application built with Flask. The application is containerized using Docker and is designed to be deployed on Google Cloud Run.

## Application

The application logic is contained in `app/app.py`. It defines a Flask application with a single route (`/`) that returns a JSON response.

## Docker

The `Dockerfile` describes how to build a Docker image for the application. It starts from a base image of Python 3.7, copies the application code and requirements file into the image, installs the Python dependencies, and specifies that the application should be run with Gunicorn when the container starts.

## Google Cloud Build

The `cloudbuild.yaml` file defines a Google Cloud Build pipeline for building the Docker image, pushing it to the Google Container Registry, deploying the image to Google Cloud Run, and performing some additional steps such as fetching the build log and creating a zip file of artifacts.


## Deployment

The application is designed to be deployed on Google Cloud Run, a managed platform that automatically scales your stateless containers. The Google Cloud Build pipeline defined in `cloudbuild.yaml` handles the deployment.
