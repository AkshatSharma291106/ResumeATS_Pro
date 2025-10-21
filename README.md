ResumeATS Pro - Resume Parser & ATS Scorer
Overview
ResumeATS Pro is a Java-based desktop application that helps job seekers optimize their resumes for Applicant Tracking Systems (ATS). The application analyzes resume content against job descriptions and provides a compatibility score based on keyword matching.

Features
Current Features
User authentication system with registration and login

Modern dark-themed user interface

Resume file upload support (TXT format)

Job description input and analysis

ATS score calculation based on keyword matching

Detailed score breakdown with statistics

Progress indicators for file processing

MySQL database integration for user management

Technical Specifications
Backend: Java 11, JDBC, MySQL

Frontend: Java Swing with FlatLaf for modern UI

Build Tool: Apache Maven

Database: MySQL 9.4

Architecture: MVC pattern with Swing components

Installation Guide
Prerequisites
Java Development Kit (JDK) 11 or higher

MySQL Server 9.4

Apache Maven 3.6+

Database Setup
Start MySQL service

Create the application database:

sql
CREATE DATABASE resume_ats_pro;
Update database credentials in LoginPagePro.java:

java
private static final String DB_PASSWORD = "your_mysql_password";
Build and Run
Clone or download the project files

Navigate to project directory:

bash
cd ResumeATS_Pro
Compile the project:

bash
mvn clean compile
Run the application:

bash
mvn exec:java
Project Structure
text
ResumeATS_Pro/
├── pom.xml
├── src/
│   └── main/
│       └── java/
│           └── com/
│               └── example/
│                   └── pro/
│                       ├── LoginPagePro.java
│                       └── ResumeATSPro.java
└── target/ (generated)
Usage Instructions
1. User Registration
Launch the application

Click "Register" to create a new account

Enter username and password (minimum 3 characters for username, 4 for password)

Registration automatically creates your user profile in the database

2. User Login
Enter registered credentials

Click "Login" to access the main application

Session maintains user context throughout the application

3. Resume Upload
Click "Upload Resume" button

Select a text file (.txt) containing your resume content

Supported content: plain text resumes

File processing includes progress indication

4. Job Description Analysis
Paste the job description in the designated text area

Ensure the description includes relevant keywords and requirements

The system will analyze against your uploaded resume

5. ATS Score Calculation
Click "Calculate ATS Score" to generate compatibility results

View detailed breakdown including:

Overall match percentage

Keyword statistics

Matching keyword list

Improvement recommendations

ATS Scoring Algorithm
Keyword Extraction
Processes text by splitting into individual words

Filters out common stop words (the, and, for, etc.)

Considers words longer than 2 characters as potential keywords

Converts all text to lowercase for case-insensitive matching

Score Calculation
text
ATS Score = (Number of Matching Keywords / Total Job Description Keywords) * 100
Score Interpretation
80-100%: Excellent match - resume is well optimized

60-79%: Good match - consider adding more relevant keywords

40-59%: Average match - review job description for missing skills

0-39%: Poor match - major keyword gaps detected

Database Schema
Users Table
sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
File Support
Currently Supported
Text files (.txt) - Full support with direct content parsing

Planned Support
PDF documents (.pdf) - Future implementation

Word documents (.docx, .doc) - Future implementation

Customization
UI Themes
The application supports multiple themes through FlatLaf:

Dark theme (default)

Light theme

Custom color schemes

Stop Words Customization
Modify the STOP_WORDS set in ResumeATSPro.java to add or remove filtered words based on specific industry requirements.

Troubleshooting
Common Issues
Database Connection Failed

Verify MySQL service is running

Check database credentials in LoginPagePro.java

Ensure resume_ats_pro database exists

File Upload Errors

Use plain text (.txt) files only

Check file permissions

Ensure file is not open in another program

Compilation Errors

Verify JDK 11+ installation

Check Maven configuration

Ensure all dependencies in pom.xml

Performance Tips
Keep resume files under 5000 characters for optimal performance

Use focused job descriptions for accurate scoring

Regular database maintenance for user management

Development
Adding New Features
Follow MVC pattern for new components

Maintain database connection best practices

Use SwingWorker for long-running operations

Implement proper exception handling

Code Structure
LoginPagePro.java: Handles user authentication and registration

ResumeATSPro.java: Main application with resume processing and scoring

Database operations use PreparedStatement for security

Swing components with modern FlatLaf styling

License
This project is for educational and personal use. Commercial use may require additional licensing.

Support
For technical support or feature requests, refer to the application documentation or contact the development team.

Version History
Version 2.0: Enhanced UI, progress indicators, detailed scoring

Version 1.0: Basic ATS scoring with text file support

