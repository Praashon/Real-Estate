# 🏘️ Real Estate App - Django Property Management Platform

<div align="center">

![Django](https://img.shields.io/badge/Django-5.2-green.svg)
![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Channels](https://img.shields.io/badge/Channels-WebSocket-orange.svg)
![Redis](https://img.shields.io/badge/Redis-Cache-red.svg)
![AI](https://img.shields.io/badge/AI-ML_Powered-purple.svg)

*An intelligent real estate platform with AI-powered search and real-time chat*

[Demo](#) | [Documentation](#) | [Report Bug](#)

</div>

## 📋 Overview

A comprehensive real estate management platform built with Django, featuring AI-powered property recommendations, real-time chat functionality, advanced search capabilities, and a complete admin dashboard. This application leverages machine learning for intelligent property matching and WebSocket technology for instant communication between buyers, sellers, and agents.

## ✨ Key Features

### Property Management
- 🏠 **Property Listings** - Comprehensive property database with detailed information
- 📸 **Image Gallery** - Multiple images per property with Pillow processing
- 🔍 **Advanced Search** - Filter by location, price, type, amenities
- 🗺️ **Location Based** - Geographic property search
- ⭐ **Featured Listings** - Highlight premium properties
- 📊 **Property Analytics** - Track views and engagement

### AI & Machine Learning
- 🤖 **Smart Recommendations** - AI-powered property suggestions using:
  - **Sentence Transformers** - Semantic similarity matching
  - **scikit-learn** - Machine learning algorithms
  - **PyTorch** - Deep learning models
  - **Hugging Face** - Pre-trained models
- 🎯 **Personalized Search** - Learn from user preferences
- 📈 **Price Prediction** - ML-based property valuation
- 🔮 **Trend Analysis** - Market insights and predictions

### Real-Time Features
- 💬 **Live Chat** - WebSocket-based instant messaging
- 🔔 **Notifications** - Real-time alerts for new properties
- 👥 **Multi-user Chat** - Group conversations
- 📱 **Online Status** - See who's available
- 🔄 **Auto-Updates** - Live property status changes

### User Management
- 🔐 **Authentication** - Secure user registration and login
- 👤 **User Profiles** - Customizable user accounts
- 🏢 **Agent Profiles** - Dedicated agent/realtor accounts
- 📝 **Saved Properties** - Bookmark favorite listings
- 📧 **Email Notifications** - Property alerts and updates

### Admin Panel
- 📊 **Dashboard** - Comprehensive admin interface
- 🏘️ **Property Management** - CRUD operations
- 👥 **User Management** - Manage buyers, sellers, agents
- 📈 **Analytics** - Sales and engagement metrics
- 🔧 **System Configuration** - App settings and preferences

## 🛠️ Tech Stack

### Backend
- **Django 5.2.1** - High-level Python web framework
- **Django Channels 4.2** - WebSocket and async support
- **Daphne 4.2** - ASGI server for Django Channels
- **Redis 6.2** - In-memory data structure store for caching

### AI/ML Stack
- **PyTorch 2.7** - Deep learning framework
- **Transformers 4.52** - Hugging Face transformers
- **Sentence Transformers 4.1** - Semantic text embeddings
- **scikit-learn 1.6** - Machine learning library
- **NumPy 2.2** - Numerical computing
- **SciPy 1.15** - Scientific computing

### Additional Technologies
- **Pillow 11.2** - Image processing
- **python-decouple 3.8** - Environment management
- **Twisted 24.11** - Event-driven networking
- **channels_redis 4.2** - Redis channel layer
- **PyYAML 6.0** - YAML parser

## 📦 Installation

### Prerequisites

- Python 3.10 or higher
- Redis server
- PostgreSQL or SQLite
- pip package manager
- Virtual environment (recommended)

### Setup Instructions

1. **Clone the Repository**
```bash
git clone https://github.com/yourusername/real-estate-app.git
cd Real-Estate/real_estate_app
```

2. **Create Virtual Environment**
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Linux/Mac
source venv/bin/activate
```

3. **Install Dependencies**
```bash
pip install -r requirements.txt
```

4. **Configure Environment Variables**

Create `.env` file in the project root:
```env
# Django Settings
SECRET_KEY=your_secret_key_here
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1

# Database
DATABASE_URL=sqlite:///db.sqlite3
# OR PostgreSQL
# DATABASE_URL=postgresql://user:password@localhost:5432/realestate

# Redis (for Channels)
REDIS_URL=redis://localhost:6379/0

# Email Configuration
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USE_TLS=True
EMAIL_HOST_USER=your_email@gmail.com
EMAIL_HOST_PASSWORD=your_app_password

# AI/ML Settings
MODEL_PATH=./models/
ENABLE_ML_RECOMMENDATIONS=True
```

5. **Install and Start Redis**

Windows:
```bash
# Download Redis for Windows or use WSL
# Or use Docker
docker run -d -p 6379:6379 redis
```

Linux/Mac:
```bash
# Install Redis
sudo apt-get install redis-server  # Ubuntu/Debian
brew install redis                  # macOS

# Start Redis
redis-server
```

6. **Run Migrations**
```bash
python manage.py makemigrations
python manage.py migrate
```

7. **Create Superuser**
```bash
python manage.py createsuperuser
```

8. **Load Sample Data** (Optional)
```bash
python manage.py loaddata fixtures/sample_properties.json
```

9. **Start the Development Server**
```bash
# For development with auto-reload
python manage.py runserver

# For production-like environment
daphne -b 0.0.0.0 -p 8000 real_estate_app.asgi:application
```

Or use the provided batch file (Windows):
```bash
start_server.bat
```

10. **Access the Application**
- Main site: `http://localhost:8000`
- Admin panel: `http://localhost:8000/admin`

## 🎯 Usage

### For Property Seekers

1. **Browse Properties**
   - View all available properties
   - Use filters to narrow down search
   - View detailed property information

2. **AI-Powered Search**
   - Describe your ideal property in natural language
   - Get intelligent recommendations based on preferences
   - Discover similar properties

3. **Save Favorites**
   - Bookmark properties you like
   - Get alerts when prices change
   - Compare saved properties

4. **Contact Agents**
   - Use real-time chat to connect with agents
   - Schedule property viewings
   - Ask questions instantly

### For Property Owners/Agents

1. **List Properties**
   - Add new property listings
   - Upload multiple images
   - Set pricing and details

2. **Manage Listings**
   - Edit property information
   - Mark as sold/rented
   - Track property views

3. **Communicate with Buyers**
   - Respond to inquiries in real-time
   - Manage multiple conversations
   - Share property details

### For Administrators

1. **Dashboard Access**
   - Login to admin panel
   - View analytics and metrics
   - Monitor system health

2. **Content Management**
   - Approve/reject listings
   - Manage user accounts
   - Moderate chat messages

3. **System Configuration**
   - Configure AI models
   - Adjust search parameters
   - Set up email templates

## 📁 Project Structure

```
Real-Estate/
├── real_estate_app/
│   ├── accounts/              # User authentication & profiles
│   │   ├── models.py         # User models
│   │   ├── views.py          # Auth views
│   │   └── urls.py           # Auth URLs
│   │
│   ├── properties/           # Property listings
│   │   ├── models.py         # Property models
│   │   ├── views.py          # Property views
│   │   ├── serializers.py    # API serializers
│   │   └── urls.py           # Property URLs
│   │
│   ├── chat/                 # Real-time chat
│   │   ├── consumers.py      # WebSocket consumers
│   │   ├── routing.py        # WebSocket routing
│   │   └── models.py         # Chat models
│   │
│   ├── search/               # Search functionality
│   │   ├── views.py          # Search views
│   │   ├── utils.py          # Search utilities
│   │   └── ml_engine.py      # AI/ML search engine
│   │
│   ├── admin_panel/          # Admin dashboard
│   │   ├── views.py          # Admin views
│   │   └── templates/        # Admin templates
│   │
│   ├── core/                 # Core app functionality
│   │   ├── settings.py       # Django settings
│   │   ├── urls.py           # URL configuration
│   │   ├── asgi.py           # ASGI config
│   │   └── wsgi.py           # WSGI config
│   │
│   ├── templates/            # HTML templates
│   │   ├── base.html         # Base template
│   │   ├── home.html         # Homepage
│   │   ├── properties/       # Property templates
│   │   └── chat/             # Chat templates
│   │
│   ├── static/               # Static files
│   │   ├── css/
│   │   ├── js/
│   │   └── images/
│   │
│   ├── media/                # User uploads
│   │   └── properties/       # Property images
│   │
│   ├── models/               # ML models (if applicable)
│   │
│   ├── manage.py             # Django management
│   ├── requirements.txt      # Python dependencies
│   ├── start_server.bat      # Quick start script
│   └── .env.example          # Environment template
│
└── README.md                 # This file
```

## 🤖 AI/ML Features

### Property Recommendation System

The app uses advanced NLP and machine learning:

```python
from sentence_transformers import SentenceTransformer
from sklearn.metrics.pairwise import cosine_similarity

# Load pre-trained model
model = SentenceTransformer('all-MiniLM-L6-v2')

# Generate embeddings
property_embeddings = model.encode(property_descriptions)
query_embedding = model.encode(user_query)

# Calculate similarity
similarities = cosine_similarity(query_embedding, property_embeddings)
```

### Semantic Search

Users can search using natural language:
- "3 bedroom house near schools with a garden"
- "Modern apartment in downtown under $300k"
- "Family home with garage and pool"

### Price Prediction

ML model predicts property values based on:
- Location
- Size and features
- Market trends
- Historical data

## 💬 WebSocket Chat

### Setup

Channels configuration in `settings.py`:
```python
INSTALLED_APPS = [
    # ...
    'channels',
]

ASGI_APPLICATION = 'real_estate_app.asgi.application'

CHANNEL_LAYERS = {
    'default': {
        'BACKEND': 'channels_redis.core.RedisChannelLayer',
        'CONFIG': {
            "hosts": [('127.0.0.1', 6379)],
        },
    },
}
```

### Consumer Example

```python
from channels.generic.websocket import AsyncWebsocketConsumer
import json

class ChatConsumer(AsyncWebsocketConsumer):
    async def connect(self):
        self.room_name = self.scope['url_route']['kwargs']['room_name']
        await self.channel_layer.group_add(
            self.room_name,
            self.channel_name
        )
        await self.accept()

    async def receive(self, text_data):
        data = json.loads(text_data)
        message = data['message']
        
        await self.channel_layer.group_send(
            self.room_name,
            {
                'type': 'chat_message',
                'message': message
            }
        )
```

## 🚀 Deployment

### Production Setup

1. **Set DEBUG to False**
```python
DEBUG = False
ALLOWED_HOSTS = ['yourdomain.com']
```

2. **Configure Database**
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'realestate_db',
        'USER': 'your_user',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

3. **Static Files**
```bash
python manage.py collectstatic
```

4. **Use Gunicorn or Daphne**
```bash
# Install
pip install gunicorn daphne

# Run with Daphne (for WebSockets)
daphne -b 0.0.0.0 -p 8000 real_estate_app.asgi:application

# Or Gunicorn (without WebSockets)
gunicorn real_estate_app.wsgi:application
```

5. **Configure Nginx**
```nginx
server {
    listen 80;
    server_name yourdomain.com;

    location / {
        proxy_pass http://127.0.0.1:8000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }

    location /ws/ {
        proxy_pass http://127.0.0.1:8000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
    }

    location /static/ {
        alias /path/to/staticfiles/;
    }

    location /media/ {
        alias /path/to/media/;
    }
}
```

### Docker Deployment

```dockerfile
FROM python:3.10

WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

RUN python manage.py collectstatic --noinput

EXPOSE 8000

CMD ["daphne", "-b", "0.0.0.0", "-p", "8000", "real_estate_app.asgi:application"]
```

## 🧪 Testing

```bash
# Run all tests
python manage.py test

# Run specific app tests
python manage.py test properties

# Run with coverage
pip install coverage
coverage run manage.py test
coverage report
```

## 🤝 Contributing

Contributions welcome! Please:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Write/update tests
5. Submit a pull request

## 📝 License

This project is licensed under the MIT License - see LICENSE file for details.

## 🙏 Acknowledgments

- Django community for the excellent framework
- Hugging Face for transformer models
- Redis for caching and channels
- PyTorch for ML capabilities

## 📞 Support

- 📧 Email: mr.prashon@gmail.com
- 🐛 Issues: GitHub Issues
- 📚 Docs: Project Wiki

## 🔮 Future Enhancements

- [ ] Virtual property tours (3D/VR)
- [ ] Mortgage calculator
- [ ] Property comparison tool
- [ ] Mobile apps (iOS/Android)
- [ ] Blockchain for property records
- [ ] Advanced analytics dashboard
- [ ] Multi-language support
- [ ] Voice search
- [ ] Augmented reality previews

---

<div align="center">

**Built with ❤️ using Django, AI, and WebSockets**

*Find your dream property with intelligent search* 🏠

</div>
