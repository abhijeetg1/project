# Dockerized Python App with Nginx Load Balancing, Rate Limiting & Authentication

This project demonstrates a Docker-based setup that runs two instances of a Python web service, load-balanced by Nginx. Nginx also enforces rate limiting and basic authentication.

##  Features

- Two Python service instances running in Docker
- Nginx configured to load balance using round-robin
- Rate limiting: 10 requests per second (with burst control)
- Basic HTTP authentication using `.htpasswd`
- Docker Compose for easy orchestration


## How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/abhijeetg1/project.git
   cd project
   ```

2. **Build and run the containers**
   ```bash
   docker-compose up --build
   ```

3. **Access the service in your browser**
   ```
   http://localhost:8080
   ```

I have used htpasswd generator to create the .htpasswd file because Nginx uses HTTP Basic Authentication, which requires credentials (username and password) to be securely stored and verified. (https://www.web2generators.com/apache-tools/htpasswd-generator)
   **Credentials (Basic Auth):**
   - Username: `admin`
   - Password: `admin123`

## How It Works

- **`app.py`** – A basic Flask service that returns a simple response.
- **`Dockerfile`** – Builds a Python image with Flask installed.
- **`nginx.conf`** – Configures load balancing, authentication, and rate limiting.
- **`.htpasswd`** – Contains the encrypted credentials for basic authentication.
- **`docker-compose.yml`** – Orchestrates the app and Nginx containers.

## Rate Limiting

Nginx is configured to:
- Allow **10 requests/second**
- With a **burst of 5 extra requests**
- Excess requests are delayed, not dropped


