# 🚀 Microservice Pipeline

> A Scalable TypeScript Microservice Monorepo with API Gateway, Service Generator CLI, and Docker Support.

[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue)]()
[![Node.js](https://img.shields.io/badge/Node.js-16+-green)]()
[![Express](https://img.shields.io/badge/Express-5.x-black)]()
[![Docker](https://img.shields.io/badge/Docker-Supported-blue)]()
[![License](https://img.shields.io/badge/License-MIT-yellow)]()

---

## 📌 Overview

**Microservice Pipeline** is a powerful backend starter architecture that allows you to:

- ⚡ Build scalable microservices
- 🏗️ Generate services using CLI (`npx jugal`)
- 🌐 Use a centralized API Gateway
- 🐳 Run Redis & RabbitMQ via Docker
- 📦 Manage all services from one monorepo
- 🔧 Auto install & clean dependencies

Perfect for building production-ready distributed systems.

---

# 🏗 Architecture

```
                     ┌──────────────┐
                     │   Gateway    │
                     │  (Express)   │
                     └──────┬───────┘
                            │
        ┌───────────────────┼───────────────────┐
        │                   │                   │
  ┌────────────┐     ┌────────────┐     ┌────────────┐
  │ Service A  │     │ Service B  │     │ Service C  │
  └────────────┘     └────────────┘     └────────────┘

         Redis (Cache)        RabbitMQ (Message Broker)
```

---

# 📁 Project Structure

```
microservice-pipeline/
│
├── services/
│   └── gateway/               # API Gateway
│
├── src/
│   ├── app.ts                 # Concurrent service runner
│   ├── servers.json           # Registered services list
│   ├── install-all.ts         # Install dependencies in all services
│   └── uninstall-all.ts       # Remove all node_modules
│
├── docker-compose.yml         # Redis + RabbitMQ setup
├── dist/                      # Compiled output
├── package.json
└── tsconfig.json
```

---

# 🛠 Tech Stack

- Node.js
- Express.js
- TypeScript
- Mongoose
- Redis
- RabbitMQ
- Docker
- ts-node-dev

---

# ⚙️ Installation Guide

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/jugalsahu/microservice-pipeline.git
```

---

## 2️⃣ Navigate Into Project

```bash
cd microservice-pipeline
```

---

## 3️⃣ Install Root Dependencies

```bash
npm install
```

---

## 4️⃣ Install All Services Dependencies

```bash
npm run install-all
```

This will:

- Go inside each service
- Run `npm install`
- Prepare all microservices

---

# 🐳 Start Infrastructure (Redis + RabbitMQ)

Make sure Docker is installed.

```bash
docker-compose up -d
```

### Services Started:

| Service | Port |
|----------|-------|
| Redis | 6379 |
| RabbitMQ | 5672 |
| RabbitMQ Dashboard | 15672 |

RabbitMQ Login:

```
Username: admin
Password: admin
```

To stop services:

```bash
docker-compose down
```

---

# 🚀 Run Development Mode

```bash
npm run dev
```

This will:

- Start Gateway
- Load all registered services
- Run using `ts-node-dev`

---

# 🧪 Create a New Microservice

After setup, generate a new service:

```bash
npx jugal
```

### What happens next?

1. You enter service name
2. Folder is created inside:

```
services/your-service-name
```

3. Boilerplate includes:
   - Express setup
   - TypeScript config
   - Dockerfile
   - Environment config
   - Mongoose connection

---

# 📦 Available Scripts

| Command | Description |
|----------|-------------|
| `npx jugal` | Generate new microservice |
| `npm run install-all` | Install dependencies for all services |
| `npm run uninstall-all` | Remove node_modules from services |
| `npm run dev` | Start gateway in development mode |
| `npm run build` | Compile TypeScript |
| `docker-compose up -d` | Start Redis & RabbitMQ |
| `docker-compose down` | Stop infrastructure |

---

# 🧹 Clean All Service Dependencies

```bash
npm run uninstall-all
```

---

# 🔄 Typical Development Workflow

```bash
git clone https://github.com/jugalsahu/microservice-pipeline.git
cd microservice-pipeline
npm install
npm run install-all
docker-compose up -d
npm run dev
npx jugal
```

---

# 📋 Prerequisites

- Node.js v16+
- npm
- Docker
- Docker Compose

---

# 🧠 How It Works

- `servers.json` keeps track of all services
- `app.ts` runs them concurrently
- Gateway acts as reverse proxy
- Each service runs on its own port
- Redis used for caching
- RabbitMQ for async messaging

---

# 👨‍💻 Maintainer

**Jugal Kishore Sahu**  
📧 jugalasahu@gmail.com  
🏷️ Full Stack Developer  

---

# ⭐ Support

If you like this project:

- Star the repository
- Share it
- Contribute improvements

---

## 📝 License

MIT License
