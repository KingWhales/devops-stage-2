# Use the official Python image as the base image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Copy the requirements file
COPY requirements.txt .

# Install the Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the entire project directory
COPY . .

# Expose the port the app will run on
EXPOSE 8000

# Set the command to start the Uvicorn server
CMD ["python", "main:app", "--host", "0.0.0.0", "--port", "8000"]
