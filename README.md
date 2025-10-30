# 🧠 MoodMesh - AI-Powered Mental Health Support Platform

<div align=\"center\">

![MoodMesh Banner](https://images.unsplash.com/photo-1499209974431-9dddcece7f88?w=1200&h=300&fit=crop)

**Your 24/7 Mental Health Companion with AI-Powered Therapy & Community Support**

[![Made with React](https://img.shields.io/badge/React-19.0-61DAFB?logo=react)](https://reactjs.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.115-009688?logo=fastapi)](https://fastapi.tiangolo.com/)
[![Google Gemini](https://img.shields.io/badge/Gemini-2.5%20Flash-4285F4?logo=google)](https://deepmind.google/technologies/gemini/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

[🌟 Features](#-features) • [🚀 Getting Started](#-getting-started) • [🏗️ Tech Stack](#-tech-stack) • [📸 Screenshots](#-screenshots) • [🤝 Contributing](#-contributing)

</div>

---

## 📖 About MoodMesh

MoodMesh is a comprehensive mental health support platform that combines **AI-powered therapy**, **community support**, and **evidence-based therapeutic techniques** to provide accessible mental wellness support 24/7. Built with cutting-edge technology and designed with empathy, MoodMesh helps users track their emotional well-being, connect with supportive communities, and access immediate crisis support when needed.

### 🎯 Why MoodMesh?

- **Accessibility:** Mental health support available anytime, anywhere
- **Privacy:** Secure, confidential platform with JWT authentication
- **Evidence-Based:** Integrates CBT, DBT, and mindfulness techniques
- **Crisis Support:** Real-time crisis detection with emergency resources
- **Community:** Connect with others who understand your journey
- **Gamification:** Stay motivated with achievements and wellness stars

---

## ✨ Features

### 🌟 Core Features

#### 1. **AI Therapist Chatbot**
- 24/7 conversational AI therapist powered by **Google Gemini 2.5 Flash**
- Evidence-based therapeutic approaches (CBT, DBT, Mindfulness)
- Context-aware responses that reference user's mood history
- Suggested therapeutic techniques based on conversation analysis
- Session tracking with insights and progress monitoring

#### 2. **Mood Logging & Analytics**
- Quick mood logging with AI-generated coping strategies
- Visual analytics with mood trends and patterns
- Streak tracking for daily logging consistency
- Hourly distribution and common emotion analysis
- AI-powered insights into emotional patterns

#### 3. **Crisis Detection & Support**
- Real-time crisis keyword detection in all interactions
- Enhanced crisis analysis with severity levels (low, medium, high, critical)
- Personalized learning profile for each user
- Emergency popup with crisis hotlines and resources
- Safety plan creation and management
- Emergency contact storage

#### 4. **Community Support**
- Public and private peer support communities
- Real-time chat with Socket.IO integration
- Community creation and moderation tools
- Member management for private communities
- Safe, moderated space for sharing experiences

#### 5. **Achievements & Gamification**
- Comprehensive achievement system across 4 categories:
  - 🌱 Mood Logging achievements
  - 🔥 Streak achievements
  - 💬 Therapy session achievements
  - 👥 Community engagement achievements
- Progress tracking with visual indicators
- Wellness stars for motivation
- Special badges (Early Bird, Night Owl, Explorer)

#### 6. **Meditation & Breathing Exercises**
- Guided breathing exercises (Box Breathing, 4-7-8, Deep Breathing)
- Meditation content library organized by category
- Session tracking and completion rewards
- Wellness stars for completed exercises

#### 7. **Resource Library**
- Educational articles on mental health conditions
- Therapeutic technique guides (CBT, DBT, Mindfulness)
- Video resources and recommended reading
- Mental health myth-busting content
- Bookmark functionality for favorite resources

#### 8. **AI Trainer (Personalized Learning)**
- Machine learning that adapts to individual users
- Personal crisis trigger detection
- Baseline emotional patterns
- Escalation history tracking
- Effective coping strategy recommendations

---

## 🏗️ Tech Stack

### Frontend
- **Framework:** React 19.0
- **Styling:** TailwindCSS 3.4 with custom animations
- **UI Components:** Radix UI primitives (Dialog, Dropdown, Toast, etc.)
- **Charts:** Recharts for analytics visualization
- **Routing:** React Router DOM 7.5
- **Real-time:** Socket.IO Client
- **Forms:** React Hook Form with Zod validation
- **Icons:** Lucide React

### Backend
- **Framework:** FastAPI (Python)
- **Database:** MongoDB (Motor async driver)
- **AI Model:** Google Gemini 2.5 Flash
- **Authentication:** JWT with bcrypt password hashing
- **Real-time:** Socket.IO AsyncServer
- **Email:** SMTP integration for emergency alerts
- **Environment:** Python-dotenv for configuration

### DevOps & Tools
- **Package Manager:** Yarn
- **Build Tool:** CRACO (Create React App Configuration Override)
- **Linting:** ESLint with React plugins
- **CSS Processing:** PostCSS with Autoprefixer

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** (v18+ recommended)
- **Python** (v3.11+)
- **MongoDB** (local or Atlas)
- **Yarn** package manager
- **Google Gemini API Key**

### Installation

#### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/moodmesh.git
cd moodmesh
```

#### 2. Backend Setup

```bash
cd backend

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Create .env file
cat > .env << EOF
MONGO_URL=mongodb://localhost:27017/
DB_NAME=moodmesh
GEMINI_API_KEY=your_gemini_api_key_here
JWT_SECRET_KEY=your_secret_key_here
JWT_ALGORITHM=HS256
JWT_EXPIRATION_HOURS=720
EOF

# Run the server
uvicorn server:app --host 0.0.0.0 --port 8000 --reload
```

#### 3. Frontend Setup

```bash
cd frontend

# Install dependencies
yarn install

# Create .env file
cat > .env << EOF
REACT_APP_BACKEND_URL=http://localhost:8000
EOF

# Start development server
yarn start
```

#### 4. Access the Application

- **Frontend:** http://localhost:3000
- **Backend API:** http://localhost:8000

### 🔑 Getting a Gemini API Key

1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Click \"Create API Key\"
4. Copy the key and add it to your backend `.env` file

---

## 🌐 API Endpoints

### Authentication
- `POST /api/auth/register` - Create new user account
- `POST /api/auth/login` - User login
- `GET /api/auth/verify` - Verify JWT token

### Mood Logging
- `POST /api/mood/log` - Log a mood entry
- `GET /api/mood/logs/{user_id}` - Get user's mood logs
- `GET /api/mood/analytics/{user_id}` - Get analytics data

### AI Therapist
- `POST /api/therapist/chat` - Send message to AI therapist
- `GET /api/therapist/history/{user_id}` - Get chat history
- `GET /api/therapist/insights/{user_id}` - Get AI-powered insights

### Communities
- `POST /api/communities/create` - Create community
- `GET /api/communities/list/{user_id}` - List available communities
- `POST /api/communities/join` - Join a community
- `GET /api/chat/messages/{room_id}` - Get community messages

### Crisis Support
- `POST /api/crisis/safety-plan` - Create/update safety plan
- `GET /api/crisis/safety-plan/{user_id}` - Get safety plan
- `POST /api/crisis/emergency-contacts` - Add emergency contact
- `POST /api/crisis/analyze` - Analyze text for crisis indicators

### Achievements & Progress
- `GET /api/achievements/{user_id}` - Get user achievements
- `GET /api/profile/{user_id}` - Get user profile

### Meditation & Resources
- `GET /api/meditation/breathing-exercises` - List breathing exercises
- `GET /api/meditation/meditations` - List meditation content
- `GET /api/resources/list` - Get resource library
- `POST /api/resources/bookmark` - Bookmark a resource

---

## 🧪 Testing

### Backend Tests

```bash
cd backend
pytest backend_test.py -v
```

### Frontend Tests

```bash
cd frontend
yarn test
```

### Test Coverage

- ✅ Authentication flow (register, login, token verification)
- ✅ Mood logging and analytics
- ✅ AI therapist chat functionality
- ✅ Crisis detection system
- ✅ Community creation and joining
- ✅ Achievement tracking
- ✅ Safety plan management

---

## 🔐 Security Features

- **JWT Authentication:** Secure token-based authentication
- **Password Hashing:** bcrypt with salt for password security
- **CORS Protection:** Configured CORS middleware
- **Input Validation:** Pydantic models for request validation
- **Crisis Monitoring:** Real-time detection of concerning language
- **Private Communities:** Password-protected group spaces
- **Data Privacy:** No personal health information shared without consent

---

## 🎨 Design Philosophy

MoodMesh follows a **calming, accessible, and empowering** design approach:

- **Color Palette:** Soothing blues, teals, and emerald greens
- **Typography:** EB Garamond for headers (elegant, readable)
- **Spacing:** Generous whitespace for reduced cognitive load
- **Accessibility:** High contrast ratios, clear CTAs, semantic HTML
- **Responsive:** Mobile-first design that works on all devices
- **Micro-interactions:** Smooth animations and feedback

---

## 🤝 Contributing

We welcome contributions from the community! Here's how you can help:

### Ways to Contribute

- 🐛 Report bugs and issues
- 💡 Suggest new features or improvements
- 📝 Improve documentation
- 🎨 Enhance UI/UX design
- 🔧 Submit pull requests

### Development Workflow

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Code Style Guidelines

- **Frontend:** Follow ESLint configuration, use functional components
- **Backend:** Follow PEP 8 style guide, add type hints
- **Commits:** Use conventional commit messages
- **Testing:** Add tests for new features

---

## 📜 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **Google Gemini AI** for powering our AI therapist
- **Radix UI** for accessible component primitives
- **TailwindCSS** for utility-first styling
- **FastAPI** for modern Python web framework
- **MongoDB** for flexible data storage
- Mental health professionals who inspired our therapeutic approach
- The open-source community for amazing tools and libraries

--

## 👥 Team

**MoodMesh Development Team**

- Lead Developer & Designer
- AI/ML Specialist
- Backend Engineer
- UI/UX Designer

---

## 🗺️ Roadmap

### Phase 1 (Current) ✅
- [x] Core mood logging functionality
- [x] AI therapist with Gemini integration
- [x] Crisis detection system
- [x] Community features
- [x] Basic analytics

### Phase 2 (In Progress) 🚧
- [ ] Mobile app (React Native)
- [ ] Voice-enabled therapy sessions
- [ ] Group therapy rooms
- [ ] Professional therapist marketplace
- [ ] Advanced ML personalization

### Phase 3 (Future) 🔮
- [ ] Wearable device integration (heart rate, sleep)
- [ ] Multilingual support (10+ languages)
- [ ] Insurance integration
- [ ] Clinical trial partnerships
- [ ] Blockchain-based anonymous data sharing

---

## 🌟 Star History

If you find MoodMesh helpful, please consider giving it a star ⭐ on GitHub!

---

## 💌 Contact

For questions, feedback, or collaboration opportunities:

- **Linkedin:** [https://www.linkedin.com/in/abdullah-hussain-70892338a](https://www.linkedin.com/in/abdullah-hussain-70892338a)
- **GitHub Issues:** [github.com/yourusername/moodmesh/issues](https://github.com/yourusername/moodmesh/issues)

---

<div align=\"center\">

**Made with ❤️ and 🧠 for Mental Health Awareness**

*MoodMesh - Because everyone deserves support*

</div>

