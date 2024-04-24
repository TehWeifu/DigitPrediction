FROM python:3.9-alpine

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install packages
RUN pip install tensorflow
RUN pip install flask
RUN pip install flask-cors
RUN pip install opencv-python

# Make port 5000 available to the world outside this container
EXPOSE 5000

ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0

CMD ["flask", "run"]
