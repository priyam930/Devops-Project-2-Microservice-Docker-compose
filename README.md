
# Devops-Project-2-Microservice-Docker-compose
🐳 Multi-Service Flask App with Docker Compose, PostgreSQL, and Redis

This project demonstrates a microservices-based backend architecture using:

🔹 Flask for REST API development

🟠 PostgreSQL for persistent data storage

🔵 Redis for in-memory caching

🐳 Docker Compose for container orchestration

Each component runs in its own container, and services communicate over a shared Docker network.

📦 Project Structure

📁 microservices-docker-app/
├── 📁 user_service/                # Service responsible for user registration
│   ├── 📝 app.py                  # Flask application logic for user handling
│   ├── 🐳 Dockerfile              # Docker build file for the user service
│   └── 📄 requirements.txt        # Python dependencies for user service
│
├── 📁 data_service/               # Service to retrieve user data and utilize Redis cache
│   ├── 📝 app.py                  # Flask application logic for data fetching
│   ├── 🐳 Dockerfile              # Docker build file for the data service
│   └── 📄 requirements.txt        # Python dependencies for data service
│
├── 🐳 docker-compose.yml         # Manages and orchestrates all services
└── 📘 README.md                   # Project documentation

🚀 Getting Started

1. Clone the Repository

git clone https://github.com/your-username/microservices-docker-app.git
cd microservices-docker-app

2. Build and Run All Services

docker-compose up --build

Docker will pull the necessary images, build your Flask apps, and start all services including PostgreSQL and Redis.

🔗 Service Endpoints

Service

Endpoint

Description

User Service

http://127.0.0.1:5000/register

Register a new user

Data Service

http://127.0.0.1:5001/user/<name>

Retrieve user info (cached with Redis)

🧪 How to Use

✅ Insert User into Database (via User Service)

curl -X POST -H "Content-type: application/json" \
http://127.0.0.1:5000/register \
-d '{"name": "priyam", "email": "priyamsanodiya340@gmail.com"}'

This command sends a POST request to register a user and stores the information in PostgreSQL.

🔍 Fetch User Data (via Data Service)

curl http://127.0.0.1:5001/user/priyam

The first request will query the PostgreSQL database and cache the result in Redis.Subsequent requests will fetch the data directly from Redis for faster response.

⚙️ Environment Details

Python 3.9+

Flask

PostgreSQL 13

Redis 6

Docker & Docker Compose

📈 Future Enhancements

Add JWT-based authentication

Integrate CI/CD using GitHub Actions or Jenkins

Add monitoring (Prometheus + Grafana)

Prepare for cloud deployment (AWS/GCP)

🙏 Credits

Special thanks to my mentors:

Vimal Daga Sir

Preeti Chandak Ma’am

Jibbran Ali Sir

For their guidance and constant support during this project journey.

📎 License

This project is open-source and available under the MIT License.

📬 Connect with Me

🌐 Portfolio: priyam-sanodiya.netlify.app

💼 LinkedIn: linkedin.com/in/priyamsanodiya

