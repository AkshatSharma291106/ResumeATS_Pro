ResumeATS Pro
A professional Java-based desktop application that helps job seekers optimize their resumes for Applicant Tracking Systems (ATS). Analyze resume compatibility with job descriptions and improve your job application success rate.

🚀 Features
User Authentication - Secure registration and login system

Modern UI - Clean, dark-themed interface built with Java Swing and FlatLaf

Resume Analysis - Upload and parse resume content from text files

ATS Scoring - Calculate compatibility scores between resumes and job descriptions

Keyword Matching - Advanced keyword extraction and matching algorithm

Progress Tracking - Visual progress indicators for file processing

Database Integration - MySQL backend for user management and data persistence

📋 Prerequisites
Java Development Kit (JDK) 11 or higher

MySQL Server 8.0 or higher

Apache Maven 3.6+

🛠️ Installation
1. Clone the Repository
bash
git clone https://github.com/yourusername/ResumeATS_Pro.git
cd ResumeATS_Pro
2. Database Setup
sql
CREATE DATABASE resume_ats_pro;
3. Configure Database
Update the database credentials in src/main/java/com/example/pro/LoginPagePro.java:

java
private static final String DB_PASSWORD = "your_mysql_password";
4. Build and Run
bash
# Compile the project
mvn clean compile

# Run the application
mvn exec:java
📁 Project Structure
ResumeATS_Pro/
├── src/main/java/com/example/pro/
│   ├── LoginPagePro.java      # Authentication and user management
│   └── ResumeATSPro.java      # Main application with ATS scoring
├── pom.xml                    # Maven configuration
└── README.md
💻 Usage
Getting Started
Register a new account or login with existing credentials

Upload your resume as a text file (.txt)

Paste the job description you're targeting

Calculate your ATS score to see compatibility results

Review detailed analysis and improvement suggestions

ATS Scoring System
The application calculates scores based on keyword matching:

Excellent (80-100%): Strong match with job requirements

Good (60-79%): Good alignment, minor improvements needed

Average (40-59%): Moderate match, consider adding relevant skills

Needs Work (0-39%): Significant keyword gaps detected

🔧 Technical Details
Built With
Java 11 - Core application logic

Swing - User interface framework

FlatLaf - Modern look and feel

MySQL - Database management

JDBC - Database connectivity

Maven - Build automation and dependency management

Algorithm
The ATS scoring uses intelligent keyword extraction:

Filters common stop words

Processes text case-insensitively

Matches resume keywords against job requirements

Provides detailed statistical breakdown

🎯 Key Components
LoginPagePro
User registration and authentication

Database connection management

Secure credential validation

ResumeATSPro
File upload and processing

Job description analysis

ATS score calculation

Results visualization

📊 Sample Workflow
User Registration → Database storage of credentials

Resume Upload → Text file parsing and content extraction

Job Analysis → Keyword extraction from job description

Score Calculation → Compatibility percentage and matching keywords

Results Display → Detailed breakdown with improvement suggestions

🐛 Troubleshooting
Common Issues
Database Connection Failed

Verify MySQL service is running

Check database credentials

Ensure database resume_ats_pro exists

File Upload Issues

Use .txt files for guaranteed compatibility

Check file permissions

Ensure files are not corrupted

Build Errors

Verify JDK 11+ installation

Check Maven configuration

Ensure all dependencies are resolved

🔮 Future Enhancements
PDF and DOCX file support

AI-powered resume suggestions

Multi-language support

Export results to PDF

Resume template library

Advanced analytics dashboard

Web application version

🤝 Contributing
We welcome contributions! Please feel free to submit pull requests or open issues for bugs and feature requests.
