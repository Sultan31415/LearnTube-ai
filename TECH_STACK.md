# LearnTube - Tech Stack Documentation

## Overview
LearnTube is a full-stack web application that leverages AI to create learning experiences from YouTube videos and documents. The system uses a modern microservices architecture with containerized deployments.

---

## Architecture

**Type:** Monorepo with Frontend + Backend + Database
**Deployment:** Docker Compose orchestration
**Pattern:** REST API architecture with JWT authentication

---

## Frontend Stack

### Core Framework
- **React 18.3.1** - UI library for building component-based interfaces
- **React Router DOM 6.26.2** - Client-side routing and navigation
- **React Scripts 5.0.1** - Create React App build tooling

### UI & Styling
- **TailwindCSS 4.1.12** - Utility-first CSS framework
- **Headless UI 2.2.8** - Unstyled, accessible UI components
- **Lucide React 0.513.0** - Icon library
- **PostCSS 8.5.6** & **Autoprefixer 10.4.21** - CSS processing

### State Management & Data Fetching
- **TanStack React Query 5.83.0** - Server state management and data synchronization
- **Axios 1.9.0** - HTTP client for API requests

### Authentication
- **Clerk React 5.32.0** - Complete authentication solution with user management

### Special Features
- **React Markdown 10.1.0** - Markdown rendering
- **React Syntax Highlighter 15.6.1** - Code syntax highlighting
- **KaTeX 0.16.22** - Mathematical notation rendering
- **Remark GFM 4.0.1** - GitHub Flavored Markdown support
- **Remark Math 6.0.0** & **Rehype KaTeX 7.0.1** - Math rendering pipeline
- **ReactFlow 11.11.4** - Node-based graph visualization
- **Three.js 0.180.0** - 3D graphics library
- **React Hot Toast 2.5.2** - Notification system

### Testing
- **Jest** (via React Scripts) - JavaScript testing framework
- **React Testing Library 16.3.0** - Component testing utilities
- **Testing Library Jest DOM 6.6.3** - Custom Jest matchers
- **Testing Library User Event 13.5.0** - User interaction simulation

### Build & Development
- **Node.js 22** - Runtime environment
- **npm** - Package manager
- **Webpack** (via React Scripts) - Module bundler
- **Babel** (via React Scripts) - JavaScript compiler

---

## Backend Stack

### Core Framework
- **Django 5.2.1** - High-level Python web framework
- **Django REST Framework 3.15.2** - Toolkit for building Web APIs
- **Python 3.13** - Programming language
- **Gunicorn 23.0.0** - WSGI HTTP server for production

### Database
- **PostgreSQL 14** - Primary relational database
- **psycopg2 2.9.10** - PostgreSQL adapter for Python

### Authentication & Authorization
- **Clerk Backend API 3.0.3** - Backend authentication service integration
- **Django REST Framework SimpleJWT 5.5.0** - JWT authentication for DRF
- **PyJWT 2.9.0** - JSON Web Token implementation
- **Django Allauth 65.9.0** - Authentication, registration, account management

### AI & Machine Learning Services
- **OpenAI 1.84.0** - GPT models integration
- **Google Generative AI 0.8.5** - Gemini AI models
- **Google Gen AI 1.28.0** - Google's generative AI SDK
- **Groq 0.26.0** - Fast LLM inference
- **Cerebras Cloud SDK 1.35.0** - Cerebras AI platform integration

### Google Cloud Services
- **Google Cloud Storage 3.2.0** - Object storage
- **Google Cloud Document AI 3.6.0** - Document processing and OCR
- **Google Cloud Vision 3.10.2** - Image analysis and OCR
- **Google Cloud Core 2.4.3** - Core Google Cloud functionality
- **Google API Python Client 2.176.0** - Google APIs access

### Document Processing
- **PyMuPDF 1.26.1** - PDF parsing and manipulation
- **pdf2image 1.17.0** - PDF to image conversion
- **python-docx 1.1.2** - Microsoft Word document processing
- **pytesseract 0.3.13** - OCR (Optical Character Recognition)
- **Pillow 11.3.0** - Image processing library
- **BeautifulSoup4 4.13.4** - HTML/XML parsing

### YouTube Integration
- **youtube-transcript-api 1.1.0** - Extract YouTube video transcripts
- **yt-dlp 2024.12.13** - YouTube video downloader and metadata extractor

### Analytics & Monitoring
- **PostHog 6.1.1** - Product analytics platform
- **Simple Analytics 1.0.7** - Privacy-friendly analytics

### Payment Processing
- **Polar SDK 0.22.1** - Payment and subscription management

### API & HTTP
- **requests 2.32.3** - HTTP library
- **httpx 0.28.1** - Async HTTP client
- **httpcore 1.0.9** - Low-level HTTP transport
- **httplib2 0.22.0** - HTTP client library

### Middleware & Utilities
- **django-cors-headers 4.6.0** - CORS handling
- **django-filter 25.1** - Reusable Django app for filtering querysets
- **django-storages 1.14.4** - Custom storage backends (cloud storage)
- **python-dotenv 1.0.1** - Environment variable management
- **tenacity 8.5.0** - Retry library
- **backoff 2.2.1** - Function decoration for backoff and retry

### Data Validation & Processing
- **Pydantic 2.11.5** - Data validation using Python type annotations
- **jsonpath-python 1.0.6** - JSONPath parsing

### Security & Cryptography
- **cryptography 44.0.3** - Cryptographic recipes and primitives
- **certifi 2025.4.26** - SSL certificate bundle
- **defusedxml 0.7.1** - XML bomb protection

---

## Infrastructure & DevOps

### Containerization
- **Docker** - Container platform
- **Docker Compose** - Multi-container orchestration
  - 3 services: `db`, `backend`, `frontend`
  - Persistent volumes for PostgreSQL data
  - Custom networking configuration

### Database
- **PostgreSQL 14**
  - Container: `coursiva_prod_db`
  - Port: 5433 (host) → 5432 (container)
  - Persistent volume: `postgres_data`

### Web Servers
- **Gunicorn** - Production WSGI server
  - 3 workers
  - 300s timeout
  - 1000 max requests with jitter
- **Node.js Development Server** - Frontend dev server (port 3000)

### DNS Configuration
- Google DNS (8.8.8.8, 8.8.4.4) for backend container

### CI/CD
- **GitHub Actions** - Automated workflows (.github/workflows/ci-cd.yml)

---

## External Services & APIs

### Authentication
- **Clerk** - Complete user authentication and management platform

### AI/LLM Providers
- **OpenAI** - GPT models for text generation and analysis
- **Google Gemini** - Google's multimodal AI models
- **Groq** - Ultra-fast LLM inference
- **Cerebras** - High-performance AI computing
- **Perplexity** - AI-powered search and answers

### Cloud Services
- **Google Cloud Platform**
  - Cloud Storage - File and document storage
  - Document AI - Document processing and analysis
  - Vision AI - Image analysis and OCR

### Video Services
- **YouTube API** - Video metadata and transcript extraction
- **YouTube Transcript API** - Dedicated transcript service (paid fallback)
- **SearchAPI.io** - Search API with YouTube support (secondary fallback)

### Analytics
- **PostHog** - Product analytics and feature flags
- **Simple Analytics** - Privacy-focused web analytics

### Payment
- **Polar** - Subscription and payment processing

---

## Development Tools

### Package Management
- **npm** - Frontend dependencies
- **pip** - Python package installer

### Code Quality & Linting
- **ESLint** (React App preset) - JavaScript linting
- **Browserslist** - Target browser configuration

### Version Control
- **Git** - Source control
- **GitHub** - Repository hosting

### Environment Management
- **.env files** - Environment variable configuration
- **dotenv** - Environment loading library

---

## Project Structure

```
Learntube/
├── frontend/              # React application
│   ├── src/
│   │   ├── components/    # Reusable UI components
│   │   ├── hooks/         # Custom React hooks
│   │   ├── utils/         # Utility functions
│   │   ├── assets/        # Static assets
│   │   └── config/        # Configuration files
│   ├── Dockerfile         # Frontend container definition
│   └── package.json       # Frontend dependencies
│
├── backend/               # Django application
│   ├── backennd/          # Main Django project
│   ├── users/             # User management app
│   ├── main/              # Core application logic
│   ├── payment/           # Payment processing
│   ├── document/          # Document processing
│   ├── analytics/         # Analytics integration
│   ├── Dockerfile         # Backend container definition
│   └── requirements.txt   # Python dependencies
│
├── docker-compose.yml     # Production orchestration
├── docker-compose.dev.yml # Development orchestration
└── .env                   # Environment variables
```

---

## Key Features Enabled by Tech Stack

### AI-Powered Learning
- Multi-provider LLM integration for content generation and analysis
- Mathematical notation rendering for technical content
- Syntax highlighting for code examples

### Document Intelligence
- PDF and Word document processing
- OCR capabilities for scanned documents
- Image analysis and text extraction

### Video Learning
- YouTube transcript extraction with fallback mechanisms
- Video metadata processing
- Integration with multiple transcript providers

### User Experience
- Real-time notifications
- Interactive visualizations (graphs, 3D elements)
- Markdown-based content rendering
- Responsive design with modern UI components

### Enterprise Features
- Subscription management
- User authentication and authorization
- Analytics and usage tracking
- Cloud storage integration

### Development Experience
- Hot reload in development
- Comprehensive testing setup
- Type-safe API communication
- Containerized development environment

---

## Environment Configuration

### Required API Keys
- `CLERK_PUBLISHABLE_KEY` & `CLERK_SECRET_KEY` - Authentication
- `OPENAI_API_KEY` - GPT models
- `GROQ_API_KEY` - Groq inference
- `GEMINI_API_KEY` - Google Gemini AI
- `PERPLEXITY_KEY` - Perplexity AI

### Optional Services
- `YOUTUBE_TRANSCRIPT_API` - Enhanced transcript extraction
- `SEARCHAPI_KEY` - Fallback transcript service
- `POSTHOG_API_KEY` - Analytics tracking
- `POLAR_CHECKOUT_URL` - Payment processing

### Development Toggles
- `DISABLE_PREMIUM_CHECK` - Bypass subscription checks in development
- `DEBUG` - Django debug mode
- `ALLOWED_HOSTS` - Permitted host/domain names

---

## Performance & Scalability

### Backend Optimizations
- Gunicorn multi-worker process management
- Database connection pooling
- Request retry mechanisms with exponential backoff
- Caching with cachetools

### Frontend Optimizations
- Code splitting and lazy loading
- React Query for efficient data caching
- Optimized asset bundling
- Tree-shaking for minimal bundle size

### Infrastructure
- Containerized deployment for easy scaling
- Persistent database volumes
- DNS optimization
- Worker timeout and request limits

---

## Security Features

- JWT-based authentication
- CORS protection
- CSRF middleware
- Environment-based secrets management
- SSL/TLS certificate validation
- XML bomb protection
- Webhook signature verification

---

## Browser Support

### Production
- >0.2% market share
- Not dead browsers
- Excludes Opera Mini

### Development
- Latest Chrome, Firefox, and Safari versions

---

## Ports & Networking

- **Frontend**: 3000 (development), containerized in production
- **Backend**: 8001 (API server)
- **Database**: 5433 (host) → 5432 (container)

---

*Last Updated: February 2026*
