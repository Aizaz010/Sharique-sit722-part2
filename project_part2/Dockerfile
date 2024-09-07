# Dockerfile for book_catalog microservice
# Use a lightweight version of Python 3.9 as the base image
FROM python:3.9-slim

# Set the working directory in the container to /app
WORKDIR /app

# Copy the requirements.txt file from the host's book_catalog folder to the /app directory in the container
COPY book_catalog/requirements.txt ./

# Install the Python dependencies listed in requirements.txt without caching to keep the image size small
RUN pip install --no-cache-dir -r requirements.txt

# Copy the entire book_catalog folder from the host to the /app directory in the container
COPY book_catalog/ ./

# Expose port 8000 so the application can be accessed from outside the container
EXPOSE 8000

# Set the command to run the FastAPI app using Uvicorn, listening on all network interfaces (0.0.0.0) and port 8000
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
