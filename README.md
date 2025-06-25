🔁 Multi-Service Dockerized Project with Nginx Reverse Proxy
This repository contains two backend applications:

A Go (Golang) service

A Python service

These are containerized and routed through Nginx, also running inside a Docker container.

Nginx acts as a reverse proxy, directing requests to each service based on the URL prefix:

/service1 → Go service

/service2 → Python service

📁 Project Structure
bash
Copy
Edit
.
├── docker-compose.yml
├── nginx
│   ├── nginx.conf
│   └── Dockerfile
├── service_1                 # Golang app
│   ├── Dockerfile
│   └── README.md
├── service_2                 # Python app
│   ├── Dockerfile
│   └── README.md
└── README.md
🚀 Setup Instructions
1. Clone the repository
bash
Copy
Edit
git clone <your-repo-url>
cd <your-repo-name>
2. Run all services with Docker Compose
bash
Copy
Edit
docker-compose up --build
This command:

Builds images for the Go and Python services

Builds an Nginx reverse proxy image

Starts all containers on a bridge network

🔁 Routing Behavior
Nginx is configured to:

Forward all requests with /service1 to the Go service

Forward all requests with /service2 to the Python service

All traffic goes through the Nginx container on port 8080.

Example:
URL	Routed To
http://localhost:8080/service1	Go (service_1)
http://localhost:8080/service2	Python (service_2)
