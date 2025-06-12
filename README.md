# 🎓 Exam Management System



## 📋 Table of Contents

- [✨ Features]
- [🏗️ System Architecture]
- [🚀 Quick Start]
- [📦 Installation]
- [🔧 Configuration]
- [📱 Usage]
- [🎯 User Roles]
- [📊 Database Schema]
- [🧪 Testing]
- [📸 Screenshots]
- [📄 License](#-license)
- [👥 Authors](#-authors)


## ✨ Features

### 🎯 **Core Functionality**
- **Multi-Role Authentication** - Admin, Teacher, and Student roles with role-based access control
- **Course Management** - Create, edit, and manage academic courses
- **Exam Creation** - Flexible exam builder with multiple question types
- **Real-time Exam Taking** - Secure, timed examination interface
- **Automated Grading** - Instant results with detailed performance analytics
- **Result Management** - Comprehensive grade tracking and reporting

### 🔐 **Security Features**
- **Secure Authentication** - Password hashing and session management
- **Role-based Permissions** - Granular access control for different user types
- **Exam Security** - Time limits, attempt restrictions, and anti-cheating measures
- **Data Validation** - Comprehensive input validation and sanitization

### 📊 **Analytics & Reporting**
- **Performance Dashboard** - Visual analytics for students and teachers
- **Grade Analytics** - Detailed performance metrics and trends
- **Export Functionality** - Export results to CSV/PDF formats
- **Statistical Reports** - Class performance and exam statistics

### 🎨 **User Experience**
- **Responsive Design** - Mobile-friendly interface
- **Intuitive UI** - Clean, modern interface design
- **Real-time Updates** - Dynamic content updates without page refresh
- **Accessibility** - WCAG compliant design

---

## 🏗️ System Architecture


┌─────────────────────────────────────────────────────────────┐
│                    Presentation Layer                       │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────────────────┐│
│  │   HTML/CSS  │ │ JavaScript  │ │      Bootstrap 5        ││
│  └─────────────┘ └─────────────┘ └─────────────────────────┘│
└─────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────┐
│                   Application Layer                         │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────────────────┐│
│  │Django Views │ │   Forms     │ │      Templates          ││
│  └─────────────┘ └─────────────┘ └─────────────────────────┘│
└─────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────┐
│                   Business Logic Layer                     │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────────────────┐│
│  │Django Models│ │   Services  │ │      Utilities          ││
│  └─────────────┘ └─────────────┘ └─────────────────────────┘│
└─────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────┐
│                     Data Layer                             │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────────────────┐│
│  │   SQLite    │ │Django ORM   │ │      Migrations         ││
│  └─────────────┘ └─────────────┘ └─────────────────────────┘│
└─────────────────────────────────────────────────────────────┘


---

## 🚀 Quick Start

Get the Exam Management System up and running in just a few minutes!

### Prerequisites
- Python 3.8+ installed
- Git installed
- Basic knowledge of Django (optional)

### One-Command Setup
\`\`\`bash
# Clone and setup everything
git clone https://github.com/yourusername/exam-management-system.git
cd exam-management-system
python scripts/complete_setup.py


### Manual Setup
\`\`\`bash
# 1. Clone the repository
git clone https://github.com/yourusername/exam-management-system.git
cd exam-management-system

# 2. Create virtual environment
python -m venv exam_env
source exam_env/bin/activate  # On Windows: exam_env\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Setup database
python manage.py migrate

# 5. Create superuser
python manage.py createsuperuser

# 6. Load sample data (optional)
python scripts/seed_sample_data.py

# 7. Run the server
python manage.py runserver
\`\`\`

🎉 **That's it!** Visit `http://127.0.0.1:8000` to see your exam system in action!

---

## 📦 Installation

### System Requirements
- **Python**: 3.8 or higher
- **Django**: 4.2+
- **Database**: SQLite (default) or PostgreSQL
- **Memory**: 512MB RAM minimum
- **Storage**: 100MB free space

### Dependencies
\`\`\`txt
Django>=4.2.0
Pillow>=9.0.0
python-docx>=0.8.11
matplotlib>=3.5.0
reportlab>=3.6.0
\`\`\`

### Environment Setup
1. **Clone Repository**
   \`\`\`bash
   git clone https://github.com/yourusername/exam-management-system.git
   cd exam-management-system
   \`\`\`

2. **Virtual Environment**
   \`\`\`bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate     # Windows
   \`\`\`

3. **Install Dependencies**
   \`\`\`bash
   pip install -r requirements.txt
   \`\`\`

4. **Database Migration**
   \`\`\`bash
   python manage.py makemigrations
   python manage.py migrate
   \`\`\`

5. **Create Admin User**
   \`\`\`bash
   python manage.py createsuperuser
   \`\`\`

---

## 🔧 Configuration

### Environment Variables
Create a `.env` file in the project root:

\`\`\`env
# Django Settings
SECRET_KEY=your-secret-key-here
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1

# Database Configuration
DATABASE_URL=sqlite:///db.sqlite3

# Email Configuration (Optional)
EMAIL_BACKEND=django.core.mail.backends.smtp.EmailBackend
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USE_TLS=True
EMAIL_HOST_USER=your-email@gmail.com
EMAIL_HOST_PASSWORD=your-app-password
\`\`\`

### Settings Configuration
Key settings in `settings.py`:

```python
# Security Settings
SECURE_BROWSER_XSS_FILTER = True
SECURE_CONTENT_TYPE_NOSNIFF = True
X_FRAME_OPTIONS = 'DENY'

# Session Configuration
SESSION_COOKIE_AGE = 3600  # 1 hour
SESSION_EXPIRE_AT_BROWSER_CLOSE = True

# File Upload Settings
FILE_UPLOAD_MAX_MEMORY_SIZE = 5242880  # 5MB
DATA_UPLOAD_MAX_MEMORY_SIZE = 5242880  # 5MB
