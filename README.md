# CloudMonitor

CloudMonitor is a cloud-native monitoring application built using Flask, Docker, and Kubernetes. It provides real-time monitoring and management of infrastructure, helping organizations track system performance, identify issues proactively, and optimize resource usage.

## Features
- Real-time monitoring and data visualization
- API endpoints for data retrieval and interaction
- Containerized for consistent deployment
- Scalable and reliable using Kubernetes

## Prerequisites
- Python 3.x
- Docker
- pip (Python package installer)

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/cloudmonitor.git
cd cloudmonitor

python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
pip install -r requirements.txt


python run.py


###DockerFile

# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Make port 5000 available to the world outside this container
EXPOSE 5000

# Define environment variable
ENV FLASK_APP run.py

# Run app.py when the container launches
CMD ["flask", "run", "--host=0.0.0.0"]


##Project Structure

cloudmonitor/
│
├── app/
│   ├── __init__.py
│   └── routes.py
│
├── Dockerfile
├── requirements.txt
└── run.py
