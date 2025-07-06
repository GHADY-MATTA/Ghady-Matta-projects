# Tutoron-GPT: AI-Powered Learning Platform

Tutoron-GPT is a comprehensive, modern AI-powered tutoring platform that provides personalized, structured, and interactive learning experiences. Built using a microservices architecture with Laravel, React, Python, LangChain, LangGraph, and Gemini, it leverages multi-agent LLM orchestration to simulate a full teaching workforce.

## 🎯 Project Overview

This platform combines the power of modern web technologies with cutting-edge AI to create an intelligent learning environment. The system features:

- **Personalized Learning**: AI-driven curriculum adaptation based on user profiles and learning styles
- **Multi-Agent Architecture**: 18+ specialized AI agents working together for comprehensive education
- **Real-time Interaction**: Streaming explanations and live AI chat capabilities
- **Progress Tracking**: Detailed analytics and performance monitoring
- **Modular Design**: Scalable, maintainable codebase with clear separation of concerns

## 📁 Project Structure

```
Ai-learning-platform/
├── tutoron-gpt/                    # Main application directory
│   ├── client/                     # React frontend application
│   │   └── vite-project/           # Vite-based React app
│   ├── server/                     # Laravel backend API
│   ├── ai-agents/                  # Python AI agents and data
│   ├── docker/                     # Docker configuration (empty)
│   ├── docs/                       # Documentation (empty)
│   └── prompts/                    # AI prompt templates (empty)
├── N8N-TESTING/                    # N8N workflow testing
├── Next-Gen AI Studio Ecosystem/   # AI studio ecosystem documentation
├── merge_contacts_project/         # Contact merging utility
├── foo-testing/                    # JavaScript testing utilities
└── Various .txt files              # Learning and documentation files
```

## 🏗️ Core Components

### 1. Frontend (`tutoron-gpt/client/`)

**Technology Stack:**
- **React 19** with Vite for fast development
- **Tailwind CSS** for modern, responsive styling
- **React Router** for client-side routing
- **Axios** for API communication
- **React Icons** for UI icons

**Key Features:**
- **Authentication System**: Login/Register with Laravel Sanctum
- **Dashboard**: Protected user dashboard with service cards
- **AI Data Viewers**: 
  - Plant Agent Data Viewer (structured card display)
  - MusicGen Data Viewer (audio player + metadata)
  - SummarizeViewer (YouTube content analysis)
- **Interactive Forms**: Multi-step plant analytics questionnaire
- **Quiz System**: Dynamic quiz generation and scoring
- **Responsive Design**: Mobile-first approach with modern UI

**File Structure:**
```
client/vite-project/src/
├── api/                    # API utilities and Axios configuration
├── assets/                 # Images, logos, and static files
├── component/              # Reusable React components
│   ├── ui/                 # UI primitives (alerts, dropdowns, etc.)
│   ├── Dashboard.jsx       # Main dashboard component
│   ├── Sidebar.jsx         # Navigation sidebar
│   ├── Navbar.jsx          # Top navigation
│   ├── ServiceCardGrid.jsx # Dashboard service cards
│   ├── PlantAgentViewer.jsx # Plant agent data display
│   ├── MusicGenViewer.jsx  # Music generation data display
│   ├── SummarizeViewer.jsx # AI summary viewer
│   └── QuizViewer.jsx      # Quiz display component
├── pages/                  # Page-level components
│   ├── Home.jsx           # Landing page
│   ├── Login.jsx          # Authentication
│   ├── Register.jsx       # User registration
│   ├── LearningStyleQCM.jsx # Learning style assessment
│   └── SelfDiscoveryQuiz.jsx # Self-discovery quiz
├── App.jsx                # Main application component
└── main.jsx               # Application entry point
```

### 2. Backend (`tutoron-gpt/server/`)

**Technology Stack:**
- **Laravel 12** with PHP 8.2+
- **Laravel Sanctum** for API authentication
- **Eloquent ORM** for database operations
- **RESTful API** design

**Key Features:**
- **User Authentication**: Secure login/register with token-based auth
- **API Gateway**: Centralized API for all frontend requests
- **Data Management**: Plant analytics, quiz answers, user profiles
- **AI Integration**: Endpoints for serving AI agent data
- **File Serving**: Dynamic file access for AI-generated content

**API Endpoints:**
```
Public:
POST /api/register          # User registration
POST /api/login            # User authentication

Protected (auth:sanctum):
POST /api/logout           # User logout
GET  /api/user             # Current user info
POST /api/plant-analytics  # Store plant analytics data
GET  /api/plant-analytics  # Retrieve user's plant data
POST /api/quiz-answers     # Store quiz answers
GET  /api/quiz-answers     # Retrieve user's quiz history
GET  /api/plant-agent-data # Latest plant agent file
GET  /api/musicgen-data    # Music generation files
```

**File Structure:**
```
server/
├── app/
│   ├── Http/Controllers/   # API controllers
│   │   ├── AuthController.php
│   │   ├── PlantAnalyticsController.php
│   │   └── QuizAnswerController.php
│   └── Models/            # Eloquent models
│       ├── User.php
│       ├── PlantAnalytics.php
│       └── QuizAnswer.php
├── routes/
│   ├── api.php           # API route definitions
│   └── web.php           # Web route definitions
├── database/             # Migrations and seeders
└── config/               # Laravel configuration
```

### 3. AI Agents (`tutoron-gpt/ai-agents/`)

**Technology Stack:**
- **Python 3.10+** with virtual environments
- **LangChain** for AI agent orchestration
- **LangGraph** for multi-agent workflows
- **Google Gemini API** for AI model access
- **AudioCraft** for music generation
- **Flask** for microservices

**Key Features:**
- **Multi-Agent System**: 18+ specialized AI agents
- **Plant Analytics**: AI-powered plant/crop analysis
- **Music Generation**: AI music creation with metadata
- **Content Generation**: Dynamic lesson and quiz creation
- **Progress Tracking**: AI-driven learning analytics

**Agent Categories:**
1. **Curriculum Agents**: GoalAdvisor, ReadinessChecker, CurriculumDesigner
2. **Lesson Generation**: LessonAuthor, QuizMaster, LessonReviewer
3. **Personalization**: UserProfiler, ProgressTracker, LessonPersonalizer
4. **System Control**: SessionDirector, ContentVerifier, MemoryArchivist
5. **Auxiliary**: ClarifierBot, PromptAuditor, FallbackAgent

**File Structure:**
```
ai-agents/
├── plant_agent_data/      # Plant analysis output files
│   ├── 1_2025-06-08_15-32-42.txt
│   ├── 1_2025-06-08_15-52-10.txt
│   └── ... (timestamped files)
├── musicgen_data/         # Music generation outputs
│   ├── user_1/           # User-specific music files
│   │   ├── *.mp3         # Generated audio files
│   │   └── *.txt         # Metadata files
│   └── user_2/, user_3/, user_4/
├── agents/               # AI agent implementations
├── prompts/              # AI prompt templates
├── utils/                # Utility scripts
├── logs/                 # Agent execution logs
├── .venv/                # Python virtual environment
├── .venv-musicgen/       # Music generation venv
├── requirements.txt      # Python dependencies
├── server.py            # Main agent server
├── music_server.py      # Music generation server
└── main.py              # Entry point
```

### 4. Supporting Projects

#### N8N-TESTING (`N8N-TESTING/`)
- **Purpose**: Workflow automation testing with N8N
- **Contents**: Python request testing scripts and JSON data files
- **Use Case**: API testing and workflow validation

#### Next-Gen AI Studio Ecosystem (`Next-Gen AI Studio Ecosystem/`)
- **Purpose**: Documentation for AI studio ecosystem
- **Contents**: Comprehensive ecosystem overview and architecture documentation

#### Merge Contacts Project (`merge_contacts_project/`)
- **Purpose**: Contact data merging utility
- **Technology**: Python with JSON processing
- **Features**: Contact deduplication and merging algorithms

#### Foo Testing (`foo-testing/`)
- **Purpose**: JavaScript testing utilities
- **Contents**: Test scripts for frontend functionality

## 🚀 Setup Instructions

### Prerequisites
- **Node.js 18+** and npm
- **PHP 8.2+** and Composer
- **Python 3.10+** and pip
- **Git** for version control
- **Docker** (optional, for containerization)

### Frontend Setup
```bash
cd tutoron-gpt/client/vite-project
npm install
npm run dev
```

### Backend Setup
```bash
cd tutoron-gpt/server
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve
```

### AI Agents Setup
```bash
cd tutoron-gpt/ai-agents
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
pip install -r requirements.txt
python server.py
```

### Environment Configuration
Create `.env` files in both `server/` and `ai-agents/` directories:

**Backend (.env):**
```env
APP_NAME=TutoronGPT
APP_ENV=local
APP_KEY=your-app-key
APP_DEBUG=true
APP_URL=http://localhost:8000

DB_CONNECTION=sqlite
DB_DATABASE=database/database.sqlite

GOOGLE_GEMINI_API_KEY=your-gemini-api-key
```

**AI Agents (.env):**
```env
GOOGLE_GEMINI_API_KEY=your-gemini-api-key
FLASK_ENV=development
```

## 📖 Usage Guide

### 1. User Registration and Authentication
1. Navigate to the application
2. Click "Sign Up" to create an account
3. Verify email and log in
4. Access the protected dashboard

### 2. Dashboard Navigation
- **Service Cards**: Click any card to access specific features
- **Sidebar**: Quick access to notes and navigation
- **Plant Analytics**: Multi-step form for crop analysis
- **AI Data Viewers**: Explore plant agent and music generation data

### 3. AI-Powered Features
- **Plant Agent Data**: View structured analysis of plant/crop data
- **Music Generation**: Listen to AI-generated music and view metadata
- **Content Summarization**: Analyze YouTube content with AI
- **Quiz Generation**: Take AI-generated quizzes based on content

### 4. Learning Assessments
- **Learning Style QCM**: Determine your preferred learning style
- **Self-Discovery Quiz**: Assess your knowledge and preferences
- **Progress Tracking**: Monitor your learning journey

## 🔧 Development

### Adding New Features
1. **Frontend**: Create components in `client/vite-project/src/component/`
2. **Backend**: Add controllers in `server/app/Http/Controllers/`
3. **AI Agents**: Implement new agents in `ai-agents/agents/`
4. **Routes**: Update API routes in `server/routes/api.php`

### Testing
```bash
# Frontend testing
cd tutoron-gpt/client/vite-project
npm run test

# Backend testing
cd tutoron-gpt/server
php artisan test

# AI agents testing
cd tutoron-gpt/ai-agents
python -m pytest
```

### Deployment
The project supports Docker deployment with configurations in the `docker/` directory.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- **Google Gemini API** for AI model access
- **LangChain** for AI agent orchestration
- **Laravel** for the robust backend framework
- **React** for the modern frontend experience
- **Tailwind CSS** for beautiful, responsive design

---

**Built with ❤️ by Ghady Matta**

> "One prompt. One lesson. One learner at a time."









