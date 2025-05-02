#This line sets the base image for the container.
FROM python:3.9-slim  

#Sets the working directory inside the container to /app.
WORKDIR /app

#Copies your local app.py file from the app/ folder into the container's /app/ directory.
COPY app.py .

#Installs the Flask library inside the container.
RUN pip install flask

#Defines the default command that will run when a container starts.
CMD ["python", "app.py"]
