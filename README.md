# AI-Powered Student Achievement Intelligence Platform

An intelligent, full-stack, enterprise-grade university web application that collects, organizes, analyzes, verifies, and manages student achievements using Artificial Intelligence, Machine Learning, spaCy NLP, and OCR document intelligence.

---

## 🌟 Key Capabilities & Features

### 1. Three Role-Based Dashboards
- **Student Portal**: Submit achievements, upload certificates, live OCR extraction, ML category prediction, NLP skill tags, dynamic analytics, AI recommendations, AI Q&A assistant, digital portfolio, and official authenticated PDF portfolio export.
- **Faculty Reviewer Portal**: Verification queue, document inspection, OCR text cross-checking, AI confidence metrics, one-click approve / reject / request correction with feedback, student monitoring, department analytics, and department PDF reports.
- **Administrator Console**: Institutional oversight, manage students and faculty accounts, configure academic departments, system activity audit logs, accreditation achievement summaries, and institutional PDF digests.

### 2. Actual AI, ML, NLP & OCR Engines
- **Automatic Achievement Classification**: Scikit-Learn TF-IDF + Multinomial Naive Bayes trained on collegiate achievement records covering all 12 distinct university categories with confidence scoring and rule-based heuristic fallback.
- **OCR Certificate Extraction**: Document parser supporting PDF and image formats (PNG, JPG, JPEG) to extract student name, issuing organization, event title, dates, and skills.
- **spaCy NLP Skill Mining**: Entity and taxonomy parser extracting technical and soft competencies, domains, and activity durations.
- **Duplicate & Anomaly Defense**: SHA-256 document hashing and Jaccard similarity algorithms flag potential duplicate submissions for faculty scrutiny.
- **AI Recommendation Engine**: Personalized opportunity recommendations (Hackathons, Certifications, Competitions, Internships) tailored to student's proven skills.
- **AI Achievement Assistant**: Interactive conversational Q&A assistant answering questions on student strengths, weaknesses, and next career milestones.
- **Official PDF Portfolio & Report Generation**: Uses Python ReportLab to generate publication-grade official student transcripts, department digests, and institutional accreditation reports with cryptographic verification signatures.

### 3. Supported 12 University Achievement Categories
1. **Hackathons**
2. **Technical Competitions**
3. **Non-Technical Competitions**
4. **Research Publications**
5. **Patents**
6. **Certifications**
7. **Internships**
8. **Academic Projects**
9. **Workshops and Conferences**
10. **Volunteering and Leadership**
11. **Sports and Cultural Activities**
12. **Other Achievements**

---

## 🛠️ Technology Stack

| Layer | Technologies |
|---|---|
| **Frontend** | React 18, Tailwind CSS, Lucide React, Recharts, Vite |
| **Backend** | Python FastAPI, Uvicorn, RESTful Endpoints, JWT Auth, Bcrypt, Pydantic |
| **Database** | MongoDB (PyMongo/Motor with automatic local persistent document store fallback) |
| **AI & NLP** | Scikit-Learn, spaCy (`en_core_web_sm`), Pandas, NumPy |
| **Document & OCR** | Tesseract OCR (`pytesseract`), PyPDF, Pillow, ReportLab |

---

## 🔑 Demo Accounts for Immediate Testing

| Role | Email | Password | Persona & Capabilities |
|---|---|---|---|
| **Student** | `student@univ.edu` | `Student@123` | Alex Johnson (CSE, 3rd Year) – Has approved hackathons, publications, certifications, and pending reviews |
| **Faculty** | `faculty@univ.edu` | `Faculty@123` | Dr. Evelyn Reed (CSE Professor) – Approval queue, student monitoring, review decision tools |
| **Admin** | `admin@univ.edu` | `Admin@123` | Dr. Arthur Pendelton (Academic Dean) – Manage users, departments, audit logs, system stats |

> **Tip:** You can also use the one-click **"Switch: Student / Faculty / Admin"** buttons in the navigation bar or the quick demo buttons on the landing page for instant role switching!

### Comprehensive Demo Dataset Included (64+ records):
- **20 Sample Students** across CSE, IT, ECE, ME departments
- **5 Faculty Members** with department assignments
- **4 Academic Departments**: Computer Science and Engineering, Information Technology, Electronics & Communication, Mechanical Engineering
- **64+ Achievements** spanning all 12 categories and all approval states (Approved, Pending, Rejected, Correction Requested)
- **AI Validation flags & OCR extracted texts**
- **In-app notifications and audit activity logs**

---

## 🚀 Quick Start Guide (Windows)

### Prerequisites
- Python 3.10+ (Python 3.14 supported)
- Node.js 18+ and npm

### 1. Backend Setup
Open a terminal in the project directory:
```powershell
cd backend

# Install backend dependencies
python -m pip install -r requirements.txt

# Start FastAPI server on port 8000
python run.py
```
Backend API will be running at: `http://127.0.0.1:8000`  
Interactive Swagger API Documentation: `http://127.0.0.1:8000/docs`

### 2. Frontend Setup
Open a second terminal in the project directory:
```powershell
cd frontend

# Install dependencies if not already installed
npm install

# Start the Vite development server on port 5173
npm run dev
```
Open your browser at: `http://localhost:5173`

### 3. One-Click Batch Launchers
- Double click `start_all.bat` to launch both servers simultaneously in separate windows.
- Or use `start_backend.bat` and `start_frontend.bat` individually.

---

## 📡 RESTful API Endpoints Specification

### Authentication:
- `POST /api/auth/register` - Register a student or user account
- `POST /api/auth/login` - Authenticate user & return JWT token
- `GET /api/auth/me` - Get logged-in user profile
- `PUT /api/auth/profile` - Update user profile
- `GET /api/auth/demo-accounts` - Get demo credentials

### Student:
- `GET /api/student/profile` - Full student profile record
- `PUT /api/student/profile` - Edit permitted profile fields
- `GET /api/student/dashboard` - Overview statistics & category counts
- `GET /api/student/achievements` - Searchable & filterable achievements
- `POST /api/student/achievements` - Submit achievement for faculty review
- `GET /api/student/analytics` - Deep student Recharts analytics

### Achievements:
- `POST /api/achievements/upload` / `POST /api/achievements/upload-document` - Upload certificate, extract OCR & run ML
- `GET /api/achievements/{id}` - Get achievement details
- `PUT /api/achievements/{id}` - Edit pending achievement
- `DELETE /api/achievements/{id}` - Delete achievement
- `POST /api/achievements/check-duplicate` - SHA-256 & text similarity duplicate check

### AI & Intelligence:
- `POST /api/ai/analyze-document` - Full OCR + NLP + Classification pipeline
- `POST /api/ai/classify-achievement` - Scikit-learn text classifier
- `POST /api/ai/extract-skills` - spaCy skill & entity extraction
- `GET /api/ai/analysis/{id}` - Deep AI analysis result
- `GET /api/ai/recommendations` - Personalized student opportunity matcher
- `GET /api/ai/summary` - Dynamic AI profile summary
- `POST /api/ai/chat` - Interactive AI Achievement Assistant Q&A

### Faculty:
- `GET /api/faculty/dashboard` - Faculty overview statistics
- `GET /api/faculty/approvals` - Verification queue with OCR inspection
- `POST /api/faculty/approve/{id}` - One-click approval with score points
- `POST /api/faculty/reject/{id}` - Rejection with reviewer feedback
- `POST /api/faculty/request-correction/{id}` - Request student correction
- `GET /api/faculty/students` - Monitored students list

### Admin:
- `GET /api/admin/dashboard` - Institutional platform metrics
- `GET /api/admin/students` - Registered students directory
- `GET /api/admin/faculty` - Faculty members directory
- `GET /api/admin/departments` - Academic departments list
- `POST /api/admin/departments` - Add new academic department
- `GET /api/admin/analytics` - Multi-department analytics
- `GET /api/admin/activity-logs` - Audit trail of system actions

### Reports:
- `GET /api/reports/student/{id}` / `GET /api/reports/student-pdf` - Download official student transcript PDF
- `GET /api/reports/department/{id}` - Download department digest PDF
- `GET /api/reports/institution` - Download institutional accreditation PDF
- `GET /api/reports/portfolio` - Digital portfolio structured data

### Notifications:
- `GET /api/notifications` - Get user notifications
- `PUT /api/notifications/{id}/read` - Mark single notification as read
- `PUT /api/notifications/read-all` - Mark all notifications read

---

## 📂 Project Structure

```
int395 project/
├── backend/
│   ├── app/
│   │   ├── config.py             # Settings, 12 categories, paths, JWT config
│   │   ├── database.py           # MongoDB proxy with persistent JSON document store fallback
│   │   ├── main.py               # FastAPI application & middleware
│   │   ├── models/               # Pydantic schemas (User, Achievement, Approval)
│   │   ├── routes/
│   │   │   ├── auth.py           # Login, Register, Profile, Demo accounts
│   │   │   ├── student.py        # Student profile, dashboard, achievements, analytics
│   │   │   ├── achievements.py   # Upload, OCR, Classify, Submit, CRUD
│   │   │   ├── faculty.py        # Approvals queue, Review, Student monitoring
│   │   │   ├── admin.py          # User management, Departments, Activity logs
│   │   │   ├── analytics.py      # Student & Department Recharts analytics
│   │   │   ├── ai.py             # Recommendations, AI Assistant chat, Summary, Analysis
│   │   │   ├── reports.py        # ReportLab PDF transcript downloads
│   │   │   └── notifications.py  # User notifications
│   │   ├── services/
│   │   │   ├── ai_classifier.py  # Scikit-learn TF-IDF classifier (12 categories)
│   │   │   ├── nlp_service.py    # spaCy skills & domain extractor
│   │   │   ├── ocr_service.py    # Tesseract OCR & PDF stream extractor
│   │   │   ├── duplicate_service.py # SHA-256 & text similarity duplicate check
│   │   │   ├── recommendation_service.py # Personalized opportunity matcher
│   │   │   └── pdf_service.py    # ReportLab academic PDF generator (Student, Dept, Inst)
│   │   └── utils/
│   │       ├── security.py       # Bcrypt password hashing & JWT tokens
│   │       └── seed_data.py      # 20 students, 5 faculty, 4 depts, 50+ achievements seeder
│   ├── uploads/                  # Uploaded student certificates
│   ├── generated_reports/        # Generated transcripts
│   ├── requirements.txt
│   ├── run.py
│   ├── test_e2e.py               # 15 comprehensive automated test suites
│   └── .env.example
├── frontend/
│   ├── src/
│   │   ├── components/common/    # Navbar, Sidebar, StatCard, Badge, Modal, Toast, NotificationCenter
│   │   ├── context/              # AuthContext (JWT session management)
│   │   ├── pages/
│   │   │   ├── LandingPage.jsx   # Public commercial SaaS landing page
│   │   │   ├── AuthModal.jsx     # Login, Register, Forgot Password
│   │   │   ├── student/          # Student dashboard & modules
│   │   │   ├── faculty/          # Faculty verification queue & monitoring
│   │   │   └── admin/            # Administrative console & audit logs
│   │   ├── services/             # API client wrappers
│   │   ├── App.jsx               # Role-based orchestrator
│   │   ├── main.jsx              # Application entry point
│   │   └── index.css             # Tailwind directives & styles
│   ├── package.json
│   ├── vite.config.js
│   └── tailwind.config.js
├── start_all.bat
├── start_backend.bat
├── start_frontend.bat
└── README.md
```

---

## 🧪 Testing Verification Workflows

1. **Run End-to-End Test Suite**:
   ```powershell
   python backend/test_e2e.py
   ```
   Verifies all 15 test suites with 100% success rate:
   - Health check
   - Demo dataset seeding (20 students, 5 faculty, 4 departments, 64 achievements)
   - Student login & profile & dashboard & achievements & analytics
   - AI 12-category classification
   - spaCy NLP skill extraction
   - Achievement submission with OCR & hash calculation
   - AI Analysis endpoint
   - Faculty queue & one-click approval workflow
   - AI personalized recommendations & interactive chat
   - PDF report generation (Student transcript, Department digest, Institutional report)
   - Admin management (Users, Departments, Analytics, Activity logs)
   - In-app notification center & read status updates

2. **Manual UI Verification**:
   - Navigate to `http://localhost:5173`.
   - Use the **"Switch: Student / Faculty / Admin"** in the top bar to test each role seamlessly.
   - As **Student**: Submit an achievement, upload a certificate, view live OCR parsing, chat with the AI assistant, and download the official PDF transcript.
   - As **Faculty**: Open **Achievement Approvals**, click **Review Now**, inspect the OCR text side-by-side with student inputs, approve with score points, and export the Department Achievement Digest.
   - As **Admin**: Inspect registered student & faculty directories, manage departments, view institutional Recharts analytics, and export the Institutional Accreditation Digest.
