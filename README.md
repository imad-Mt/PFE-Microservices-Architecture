# Optimized PFE Microservices Architecture

This project implements an optimized microservices architecture for a student management system with enhanced performance, caching, and monitoring capabilities.
![Uploading serveuresxi_32734eed.gif…]()

## 🚀 Key Optimizations

### Backend (Core Service)

- **Response Caching**: Redis-based caching for frequently accessed data
- **Async Operations**: Full async/await implementation for better concurrency
- **Request Compression**: GZip compression for reduced bandwidth
- **Performance Monitoring**: Request timing and slow query detection
- **Enhanced Error Handling**: Structured error responses with proper HTTP status codes
- **Background Tasks**: Non-blocking operations for logging and cleanup
- **Bulk Operations**: Efficient batch processing for large datasets
- **Health Checks**: Comprehensive service health monitoring

### Frontend (React Router)

- **Optimized API Client**: Enhanced Axios configuration with interceptors
- **Type Safety**: Full TypeScript interfaces for all API responses
- **Error Handling**: Centralized error handling with user-friendly messages
- **Performance Monitoring**: Request timing and slow request warnings
- **Pagination Support**: Efficient data loading with pagination
- **Search & Filtering**: Advanced search capabilities

### Infrastructure

- **Redis Caching**: In-memory caching for improved response times
- **Health Monitoring**: Prometheus and Grafana for system monitoring
- **Container Orchestration**: Optimized Docker Compose setup
- **Load Balancing**: Nginx reverse proxy configuration

## 📁 Project Structure

```
pfe/
├── core/                    # Optimized FastAPI backend
│   ├── app/
│   │   ├── main.py         # Enhanced FastAPI app with middleware
│   │   ├── routes/         # Optimized API routes
│   │   ├── services/       # Business logic layer
│   │   └── models/         # Cassandra ORM models
│   ├── requirements.txt    # Enhanced dependencies
│   └── Dockerfile
├── my-app/                 # React Router frontend
│   ├── app/
│   │   ├── api/           # Optimized API client
│   │   ├── lib/           # Enhanced utilities
│   │   └── components/    # React components
│   ├── package.json
│   └── Dockerfile
├── docker-compose.yml     # Complete infrastructure setup
└── README.md
```

## 🛠 Technologies Used

### Backend

- **FastAPI**: High-performance async web framework
- **Cassandra**: Distributed NoSQL database
- **Redis**: In-memory caching and session storage
- **Pydantic**: Data validation and serialization
- **ORJSON**: Fast JSON serialization
- **Uvicorn**: ASGI server

### Frontend

- **React Router v7**: Modern React framework
- **TypeScript**: Type-safe development
- **Axios**: HTTP client with interceptors
- **Tailwind CSS**: Utility-first CSS framework
- **Radix UI**: Accessible component library

### Infrastructure

- **Docker**: Containerization
- **Redis**: Caching layer
- **Nginx**: Reverse proxy and load balancer
- **Prometheus**: Metrics collection
- **Grafana**: Monitoring dashboards

## 🚀 Quick Start

### Prerequisites

- Docker and Docker Compose
- Node.js 18+ (for local development)
- Python 3.11+ (for local development)

### 1. Clone and Setup

```bash
git clone <repository-url>
cd pfe
```

### 2. Start Services

```bash
# Start all services
docker-compose up -d

# Check service health
docker-compose ps
```

### 3. Access Applications

- **Frontend**: http://localhost:3000
- **API Documentation**: http://localhost:8000/core/docs
- **API Health**: http://localhost:8000/core/health
- **Grafana**: http://localhost:3001 (admin/admin)
- **Prometheus**: http://localhost:9090

## 📊 API Endpoints

### Students API

```typescript
// Get students with pagination and filtering
GET /core/students?page=1&limit=10&search=john&groupe_id=1&valide=true

// Get single student
GET /core/students/{id}

// Create student
POST /core/students

// Update student
PUT /core/students/{id}

// Delete student (with soft delete option)
DELETE /core/students/{id}?soft_delete=true
```
