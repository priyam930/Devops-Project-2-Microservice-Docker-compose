
# 🐳 Multi-Service Flask App with Docker Compose, PostgreSQL, and Redis

This project demonstrates a **microservices-based backend architecture** using:

- 🔹 **Flask** for REST API development  
- 🟠 **PostgreSQL** for persistent data storage  
- 🔵 **Redis** for in-memory caching  
- 🐳 **Docker Compose** for container orchestration  

Each component runs in its own container, and services communicate over a shared Docker network.

---

## 📦 Project Structure

```
.
├── user_service/           # Handles user registration
│   ├── app.py
│   ├── Dockerfile
│   └── requirements.txt
├── data_service/           # Fetches user data with Redis caching
│   ├── app.py
│   ├── Dockerfile
│   └── requirements.txt
├── docker-compose.yml      # Orchestrates all services
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/microservices-docker-app.git
cd microservices-docker-app
```

### 2. Build and Run All Services

```bash
docker-compose up --build
```

Docker will pull the necessary images, build your Flask apps, and start all services including PostgreSQL and Redis.

---

## 🔗 Service Endpoints

| Service        | Endpoint                            | Description                          |
|----------------|-------------------------------------|--------------------------------------|
| User Service   | `http://127.0.0.1:5000/register`    | Register a new user                  |
| Data Service   | `http://127.0.0.1:5001/user/<name>` | Retrieve user info (cached with Redis) |

---

## 🧪 How to Use

### ✅ Insert User into Database (via User Service)

```bash
curl -X POST -H "Content-type: application/json" \
http://127.0.0.1:5000/register \
-d '{"name": "priyam", "email": "priyamsanodiya340@gmail.com"}'
```

This command sends a POST request to register a user and stores the information in PostgreSQL.

---

### 🔍 Fetch User Data (via Data Service)

```bash
curl http://127.0.0.1:5001/user/priyam
```

The first request will query the PostgreSQL database and cache the result in Redis.  
Subsequent requests will fetch the data directly from Redis for faster response.

---

## ⚙️ Environment Details

- **Python 3.9+**
- **Flask**
- **PostgreSQL 13**
- **Redis 6**
- **Docker & Docker Compose**

---

## 📈 Future Enhancements

- Add JWT-based authentication
- Integrate CI/CD using GitHub Actions or Jenkins
- Add monitoring (Prometheus + Grafana)
- Prepare for cloud deployment (AWS/GCP)

---

## 🙏 Credits

Special thanks to my mentors:

- **Vimal Daga Sir**


For their guidance and constant support during this project journey.

---

## 📎 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 📬 Connect with Me

- 🌐 Portfolio: [priyam-sanodiya.netlify.app](https://priyam-sanodiya.netlify.app/)
- 💼 LinkedIn: [linkedin.com/in/priyamsanodiya](https://www.linkedin.com/in/priyamsanodiya/)
