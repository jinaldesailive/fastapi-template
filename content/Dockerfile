# Start from the official Python base image 3.11
FROM python:3.11-slim-buster

# Install system dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Copy requirements.txt file
COPY requirements.txt requirements.txt

# Install dependencies
RUN pip install -r requirements.txt

# Copy the rest of the project files
COPY . .

# Expose the port on which the FastAPI app will run
ENV PORT=8080
EXPOSE $PORT

# Set the command to run the uvicorn server at 8080 port.
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8080"]
