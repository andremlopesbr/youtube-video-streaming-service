# 🎥 YouTube Video Streaming Service

> Enterprise-grade video streaming platform built with hexagonal architecture, SOLID principles, and clean code practices.

[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)]()
[![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)]()
[![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)]()
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)]()
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)]()

## 📋 Overview

A scalable YouTube-like video streaming platform featuring video upload, processing, transcoding, and adaptive bitrate streaming (HLS/DASH). This project demonstrates professional software architecture patterns and best practices.

## ✨ Features

- 🎬 **Video Upload & Processing**: Multi-part upload with progress tracking
- 📹 **Adaptive Streaming**: HLS/DASH support for optimal viewing experience  
- 🔐 **Authentication**: JWT-based auth with refresh tokens
- 👤 **User Management**: Profile, subscriptions, and watch history
- 💬 **Comments & Likes**: Real-time interactions
- 🔍 **Search**: Full-text search with filters
- 📊 **Analytics**: View tracking and engagement metrics
- 🎨 **Modern UI**: Responsive design with Next.js 14

## 🏗️ Architecture

### Hexagonal Architecture (Ports & Adapters)

```
src/
├── application/          # Use cases & business logic
│   ├── ports/           # Interfaces (contracts)
│   └── use-cases/       # Application services
├── domain/              # Core business entities
│   ├── entities/        # Domain models
│   ├── value-objects/   # Immutable value types
│   └── events/          # Domain events
├── infrastructure/      # External adapters
│   ├── database/        # PostgreSQL implementation
│   ├── storage/         # S3/MinIO for videos
│   ├── queue/           # RabbitMQ/Bull
│   └── cache/           # Redis
└── presentation/        # API & Controllers
    ├── http/            # REST endpoints
    └── graphql/         # GraphQL resolvers
```

### SOLID Principles Applied

- **S**ingle Responsibility: Each class has one reason to change
- **O**pen/Closed: Open for extension, closed for modification  
- **L**iskov Substitution: Subtypes are substitutable for base types
- **I**nterface Segregation: Many specific interfaces over one general
- **D**ependency Inversion: Depend on abstractions, not concretions

## 🚀 Tech Stack

### Frontend
- Next.js 14 (App Router)
- TypeScript
- TailwindCSS
- Video.js / HLS.js
- React Query
- Zustand

### Backend  
- NestJS
- TypeScript
- PostgreSQL + Prisma
- Redis (caching)
- RabbitMQ (async processing)
- FFmpeg (video transcoding)

### DevOps
- Docker & Docker Compose
- Nginx (reverse proxy)
- MinIO (S3-compatible storage)

## 🐳 Quick Start with Docker

### Prerequisites

- Docker 24.0+
- Docker Compose 2.20+
- 8GB RAM minimum
- 20GB free disk space

### Installation

```bash
# Clone the repository
git clone https://github.com/andremlopesbr/youtube-video-streaming-service.git
cd youtube-video-streaming-service

# Copy environment files
cp .env.example .env

# Start all services
docker-compose up -d

# View logs
docker-compose logs -f
```

### Access

- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:4000
- **API Docs**: http://localhost:4000/api/docs
- **MinIO Console**: http://localhost:9001
- **RabbitMQ Management**: http://localhost:15672

## 📦 Services

| Service | Port | Description |
|---------|------|-------------|
| Frontend | 3000 | Next.js application |
| Backend | 4000 | NestJS API server |
| PostgreSQL | 5432 | Main database |
| Redis | 6379 | Cache & sessions |
| RabbitMQ | 5672, 15672 | Message queue |
| MinIO | 9000, 9001 | Object storage |
| Nginx | 80 | Reverse proxy |

## 🛠️ Development

```bash
# Install dependencies
npm install

# Run migrations
npm run db:migrate

# Seed database
npm run db:seed

# Start development
npm run dev

# Run tests
npm run test
npm run test:e2e

# Run linter
npm run lint
```

## 📚 Project Structure

```
.
├── apps/
│   ├── frontend/         # Next.js app
│   └── backend/          # NestJS API
├── packages/
│   ├── shared/           # Shared utilities
│   └── types/            # TypeScript types
├── docker/
│   ├── nginx/            # Nginx config
│   └── postgres/         # DB init scripts
├── docker-compose.yml    # Service orchestration
└── README.md
```

## 🧪 Testing

```bash
# Unit tests
npm run test:unit

# Integration tests  
npm run test:integration

# E2E tests
npm run test:e2e

# Coverage
npm run test:cov
```

## 📈 Performance

- Video transcoding with FFmpeg
- CDN-ready with HLS segmentation
- Redis caching for hot data
- Database query optimization
- Lazy loading & code splitting

## 🔒 Security

- JWT authentication
- CORS configuration
- Rate limiting
- Input validation & sanitization  
- SQL injection protection
- XSS prevention

## 🌍 Environment Variables

```env
# Database
DATABASE_URL=postgresql://user:pass@localhost:5432/streaming

# Redis
REDIS_URL=redis://localhost:6379

# MinIO
MINIO_ENDPOINT=localhost
MINIO_PORT=9000
MINIO_ACCESS_KEY=minioadmin
MINIO_SECRET_KEY=minioadmin

# JWT
JWT_SECRET=your-secret-key
JWT_EXPIRES_IN=7d
```

## 🚧 Roadmap

- [ ] Live streaming support (RTMP)
- [ ] Recommendation algorithm
- [ ] Multi-language subtitles
- [ ] Advanced analytics dashboard
- [ ] Mobile apps (React Native)
- [ ] AI-powered content moderation

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## 📝 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file.

## 👤 Author

**André Lopes**
- GitHub: [@andremlopesbr](https://github.com/andremlopesbr)
- LinkedIn: [/in/andre-lopes](https://linkedin.com/in/andre-lopes)

## 🙏 Acknowledgments

- Inspired by Full Cycle 3.0 architecture patterns
- Built following Clean Architecture principles
- Hexagonal architecture by Alistair Cockburn

---

⭐ Star this repo if you find it helpful!
