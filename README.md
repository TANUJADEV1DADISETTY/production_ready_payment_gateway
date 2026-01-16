### 🚀 Payment Gateway Platform – Deliverable 2

A production-ready payment gateway system built for scalability, reliability, and real-world payment workflows. This deliverable introduces asynchronous processing, secure webhooks, an embeddable SDK, and complete refund management.

---

## ✨ Features

- Asynchronous payment processing using Redis + Bull job queues
- Secure webhook delivery with HMAC signature verification
- Automatic webhook retries with exponential backoff
- Embeddable JavaScript SDK for seamless checkout integration
- Full and partial refund management
- Idempotency keys to prevent duplicate payments
- Enhanced dashboard with webhook configuration and API documentation
- Deterministic test mode for development and QA

---

## 🧱 Architecture Overview

Client / SDK  
→ Checkout UI (3001)  
→ API Server (8000)  
→ Redis Queue (Bull)  
→ Async Workers  
→ PostgreSQL  
→ Webhooks → Merchant Servers

Payments are processed asynchronously to improve performance and fault tolerance. Webhooks ensure reliable event delivery with retries.

---

## 🛠 Tech Stack

- Backend: Node.js + Express.js
- Job Queue: Bull (Redis-based)
- Database: PostgreSQL
- Frontend: React
- SDK: JavaScript
- Containerization: Docker & Docker Compose

---

## 📦 Prerequisites

- Docker
- Docker Compose
- Node.js 18+ (for local development)

---

## ▶️ Getting Started

### Running the Application

```bash
docker-compose up -d
docker-compose logs -f
docker-compose down
```

## 🌐 Services

- **API**: http://localhost:8000
- **Dashboard**: http://localhost:3000
- **Checkout**: http://localhost:3001
- **PostgreSQL**: localhost:5432
- **Redis**: localhost:6379

---

## 📘 API Documentation

Available via the dashboard:

http://localhost:3000/dashboard/docs

Includes:

- Payment APIs
- Refund APIs
- Webhook payloads
- Authentication details

---

## 🔁 Webhook System

- HMAC SHA-256 signature verification
- Configurable webhook endpoints
- Automatic retry with exponential backoff
- Failure-safe delivery mechanism

---

## 💸 Refund Management

- Full refunds
- Partial refunds
- Refund status tracking
- Protection against duplicate refunds

---

## 🧪 Test Mode

Environment variables for deterministic testing:

```env
TEST_MODE=true
TEST_PROCESSING_DELAY=1000
TEST_PAYMENT_SUCCESS=true
WEBHOOK_RETRY_INTERVALS_TEST=true
```
