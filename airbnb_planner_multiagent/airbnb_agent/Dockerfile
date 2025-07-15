# Use an official Python runtime as a parent image
FROM python:3.11-slim

# Set the working directory in the container
WORKDIR /app

# Copy the pyproject.toml and uv.lock files
COPY ../pyproject.toml ../uv.lock ./

# Install uv
RUN pip install uv

# Install dependencies
RUN uv sync --system

# Copy the rest of the application's code
COPY . .

# Expose the port the app runs on
EXPOSE 8000

# Define the command to run the application
CMD ["uv", "run", "."]