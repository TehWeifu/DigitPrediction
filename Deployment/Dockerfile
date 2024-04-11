# Use an official Python 3.12 runtime based on Alpine Linux as a parent image
FROM python:3.12-alpine

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY .. /app

# Install any needed packages specified in requirements.txt
# Add build dependencies for certain Python packages if necessary
RUN apk add --no-cache gcc musl-dev libffi-dev \
    && pip install --no-cache-dir -r requirements.txt \
    && apk del gcc musl-dev libffi-dev

# Make port 5000 available to the world outside this container
EXPOSE 5000

# Define environment variable
ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0

# Run myapp.py when the container launches
CMD ["flask", "run"]
