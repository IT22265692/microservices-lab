# Microservices Lab – Spring Boot + Docker

This project demonstrates a **Microservices Architecture** using:

- Spring Boot
- Spring Cloud Gateway
- Docker
- Docker Compose

The system consists of 4 services:

1. Item Service
2. Order Service
3. Payment Service
4. API Gateway

All services are containerized and communicate through the API Gateway.

---

## 🏗 Architecture

Client → API Gateway (8080) → Microservices  
- Item Service (8081)  
- Order Service (8082)  
- Payment Service (8083)

Each service runs independently inside Docker containers.

---

## ⚙ Technologies Used

- Java 17
- Spring Boot 3.x
- Spring Cloud Gateway
- Maven
- Docker
- Docker Compose

---

## 📂 Project Structure

microservices-lab/

├── item-service/
├── order-service/
├── payment-service/
├── api-gateway/
├── docker-compose.yml


---

## 🚀 How to Run

### Step 1 – Build JAR files
Inside each service folder:

mvnw.cmd clean package

### Step 2 – Build Docker Images

From root folder:

docker compose build

### Step 3 – Start All Services

docker compose up -d

---

## 🔍 Verify Containers Running

docker ps

You should see:

- item-service
- order-service
- payment-service
- api-gateway

---

## 🌐 API Testing (Through Gateway – Port 8080)

### Get Items
GET http://localhost:8080/items

### Create Item
POST http://localhost:8080/items
Body:
"Headphones"

---

### Get Orders
GET http://localhost:8080/orders

### Create Order
POST http://localhost:8080/orders
Body:
{
  "item": "Laptop",
  "quantity": 2
}

---

### Process Payment
POST http://localhost:8080/payments/process
Body:
{
  "orderId": 1,
  "amount": 1200,
  "method": "CARD"
}

---

## 🐳 Stop Containers

docker compose down

---

## 🎯 Learning Outcomes

- Designed microservices architecture
- Implemented API Gateway routing
- Containerized services using Docker
- Managed multi-container setup with Docker Compose
