# Campus Course & Records Manager (CCRM)

> Note: See `requirements.md` at the project root for build steps, Java version, and evaluation notes.

## Project Overview

The Campus Course & Records Manager (CCRM) is a comprehensive Java SE console application designed to manage campus academic operations including student management, course administration, enrollment tracking, and grade management. This application demonstrates advanced Java programming concepts, object-oriented design principles, and modern Java APIs.

## Table of Contents

1. [Project Overview](#project-overview)
2. [Evolution of Java](#evolution-of-java)
3. [Java Platform Comparison](#java-platform-comparison)
4. [Java Architecture](#java-architecture)
5. [Installation & Setup](#installation--setup)
6. [How to Run](#how-to-run)
7. [Features](#features)
8. [Technical Implementation](#technical-implementation)
9. [Project Structure](#project-structure)
10. [Syllabus Topic Mapping](#syllabus-topic-mapping)
11. [Usage Examples](#usage-examples)
12. [Screenshots](#screenshots)
13. [Contributing](#contributing)
14. [License](#license)

## Evolution of Java

### Java Timeline

- **1995**: Java 1.0 - Initial release with applets and basic OOP
- **1997**: Java 1.1 - Inner classes, JDBC, RMI
- **1998**: Java 1.2 - Collections framework, Swing, JIT compiler
- **2000**: Java 1.3 - HotSpot JVM, JavaSound
- **2002**: Java 1.4**: Regular expressions, NIO, XML processing
- **2004**: Java 5.0 - Generics, annotations, enhanced for-loop, autoboxing
- **2006**: Java 6 - Scripting support, JDBC 4.0, compiler API
- **2011**: Java 7 - Try-with-resources, diamond operator, strings in switch
- **2014**: Java 8 - Lambda expressions, Stream API, Optional, Date/Time API
- **2017**: Java 9 - Module system, JShell, HTTP/2 client
- **2018**: Java 10 - Local variable type inference (var)
- **2018**: Java 11 - LTS, HTTP client, var in lambdas
- **2019**: Java 12 - Switch expressions, text blocks preview
- **2020**: Java 14 - Records, pattern matching, text blocks
- **2021**: Java 17 - LTS, sealed classes, pattern matching for switch
- **2022**: Java 19 - Virtual threads, pattern matching for switch
- **2023**: Java 21 - LTS, virtual threads, pattern matching for switch

## Java Platform Comparison

| Feature | Java ME | Java SE | Java EE |
|---------|---------|---------|---------|
| **Target Platform** | Mobile/Embedded | Desktop/Server | Enterprise Applications |
| **JVM** | Limited JVM | Full JVM | Full JVM + EE APIs |
| **Memory** | Limited (few MB) | Standard (GB) | Standard (GB) |
| **APIs** | Subset of SE | Core Java APIs | SE + Enterprise APIs |
| **Use Cases** | Mobile apps, IoT | Desktop apps, tools | Web apps, enterprise |
| **Examples** | Android (early), embedded | Swing, console apps | Servlets, EJBs, JPA |
| **Deployment** | JAR files | JAR files | WAR/EAR files |
| **Libraries** | Minimal | Standard library | Enterprise libraries |

## Java Architecture

### JDK (Java Development Kit)
- **What**: Complete development environment for Java
- **Contains**: JRE + development tools (compiler, debugger, profiler)
- **Tools**: javac, java, javadoc, jdb, jps, jstat, etc.
- **Purpose**: Used by developers to create Java applications

### JRE (Java Runtime Environment)
- **What**: Runtime environment for executing Java applications
- **Contains**: JVM + Java class libraries + other supporting files
- **Purpose**: Required to run Java applications on end-user machines
- **Note**: JRE is included in JDK

### JVM (Java Virtual Machine)
- **What**: Virtual machine that executes Java bytecode
- **Functions**: 
  - Loads and verifies bytecode
  - Manages memory (heap, stack, method area)
  - Executes bytecode using interpreter or JIT compiler
  - Provides garbage collection
- **Platform**: Platform-specific implementation

### How They Interact
```
Developer writes Java code (.java)
    ↓
JDK compiles to bytecode (.class)
    ↓
JRE loads bytecode into JVM
    ↓
JVM executes bytecode on target platform
```

## Installation & Setup

### Windows Installation Steps

1. **Download JDK**
   - Visit [Oracle JDK](https://www.oracle.com/java/technologies/downloads/) or [OpenJDK](https://openjdk.org/)
   - Download JDK 17 or later for Windows

2. **Install JDK**
   - Run the installer as administrator
   - Follow the installation wizard
   - Note the installation path (usually `C:\Program Files\Java\jdk-17`)

3. **Set Environment Variables**
   - Open System Properties → Advanced → Environment Variables
   - Add `JAVA_HOME` variable pointing to JDK installation directory
   - Add `%JAVA_HOME%\bin` to `PATH` variable

4. **Verify Installation**
   ```cmd
   java -version
   javac -version
   ```

### Eclipse IDE Setup

1. **Download Eclipse**
   - Visit [Eclipse Downloads](https://www.eclipse.org/downloads/)
   - Download Eclipse IDE for Java Developers

2. **Create New Project**
   - File → New → Java Project
   - Enter project name: "CCRM"
   - Select Java version (17 or later)
   - Click Finish

3. **Configure Project Structure**
   - Right-click project → Properties
   - Java Build Path → Source → Add Folder
   - Create `src/main/java` folder structure

4. **Run Configuration**
   - Right-click `CCRMMain.java` → Run As → Java Application
   - Or use Run → Run Configurations → Java Application

## How to Run

### Prerequisites
- Java JDK 17 or later
- Eclipse IDE (recommended) or any Java IDE

### Running the Application

1. **Clone/Download the project**
2. **Import into Eclipse**
   - File → Import → Existing Projects into Workspace
   - Select the CCRM project folder

3. **Run the application**
   - Navigate to `src/main/java/edu/ccrm/CCRMMain.java`
   - Right-click → Run As → Java Application

4. **Command Line Execution**
   ```bash
   # Compile
   javac -d bin src/main/java/edu/ccrm/*.java src/main/java/edu/ccrm/**/*.java
   
   # Run
   java -cp bin edu.ccrm.CCRMMain
   ```

### Sample Commands
```bash
# Enable assertions (for testing)
java -ea -cp bin edu.ccrm.CCRMMain

# Run with specific memory settings
java -Xmx512m -cp bin edu.ccrm.CCRMMain
```

## Features

### Core Functionality
- **Student Management**: Add, update, search, and manage student records
- **Course Management**: Create, update, and manage academic courses
- **Enrollment System**: Enroll/unenroll students in courses with business rules
- **Grade Management**: Record grades and calculate GPAs
- **Transcript Generation**: Generate detailed academic transcripts
- **File Operations**: Import/export data in CSV and JSON formats
- **Backup System**: Create and manage data backups
- **Reporting**: Generate various academic reports

### Advanced Features
- **Search & Filter**: Advanced search capabilities using Stream API
- **Data Validation**: Comprehensive input validation and error handling
- **Business Rules**: Credit limits, enrollment constraints
- **Statistics**: GPA analysis, grade distribution, department statistics
- **Recursive Operations**: File system operations and backup management

## Technical Implementation

### Object-Oriented Programming
- **Encapsulation**: Private fields with getters/setters
- **Inheritance**: Person → Student, Person → Instructor
- **Abstraction**: Abstract Person class with abstract methods
- **Polymorphism**: Method overriding and interface implementations

### Design Patterns
- **Singleton**: AppConfig for application-wide configuration
- **Builder**: Course creation with fluent interface
- **Service Layer**: Separation of business logic from presentation

### Modern Java Features
- **Stream API**: Data processing and filtering
- **Lambda Expressions**: Functional programming constructs
- **Date/Time API**: Modern date and time handling
- **NIO.2**: Advanced file I/O operations
- **Optional**: Null-safe programming
- **Enums**: Type-safe constants with methods

### Exception Handling
- **Custom Exceptions**: DuplicateEnrollmentException, MaxCreditLimitExceededException
- **Checked vs Unchecked**: Proper exception hierarchy
- **Try-with-resources**: Automatic resource management
- **Multi-catch**: Handling multiple exception types

## Project Structure

```
CCRM/
├── src/main/java/edu/ccrm/
│   ├── CCRMMain.java                 # Main application entry point
│   ├── cli/
│   │   └── CLIMenu.java             # Command-line interface
│   ├── config/
│   │   └── AppConfig.java           # Singleton configuration
│   ├── domain/
│   │   ├── Person.java              # Abstract base class
│   │   ├── Student.java             # Student entity
│   │   ├── Instructor.java          # Instructor entity
│   │   ├── Course.java              # Course entity with Builder
│   │   ├── Enrollment.java          # Enrollment entity
│   │   ├── Semester.java            # Semester enum
│   │   ├── Grade.java               # Grade enum
│   │   ├── Persistable.java         # Interface for persistence
│   │   └── Searchable.java          # Generic search interface
│   ├── service/
│   │   ├── StudentService.java      # Student business logic
│   │   ├── CourseService.java       # Course business logic
│   │   ├── EnrollmentService.java   # Enrollment business logic
│   │   └── TranscriptService.java   # Transcript generation
│   ├── io/
│   │   ├── ImportExportService.java # File I/O operations
│   │   └── BackupService.java       # Backup management
│   └── exception/
│       ├── DuplicateEnrollmentException.java
│       └── MaxCreditLimitExceededException.java
├── test-data/
│   ├── students.csv                 # Sample student data
│   ├── courses.csv                  # Sample course data
│   └── enrollments.csv              # Sample enrollment data
├── data/                            # Application data directory
├── backups/                         # Backup storage
├── exports/                         # Export storage
└── README.md                        # This file
```

## Syllabus Topic Mapping

| Topic | File/Class/Method | Description |
|-------|------------------|-------------|
| **Java Syntax & Structure** | CCRMMain.java | Main class with proper structure |
| **Packages** | edu.ccrm.* | Organized package structure |
| **Primitive Variables** | All domain classes | int, double, boolean, String usage |
| **Objects** | Student, Course, etc. | Object creation and manipulation |
| **Operators** | Service classes | Arithmetic, relational, logical operators |
| **Decision Structures** | CLIMenu.java | if/else, switch statements |
| **Loops** | CLIMenu.java | while, for, enhanced for loops |
| **Arrays** | Service classes | Array operations and utilities |
| **Strings** | All classes | String methods and manipulation |
| **Encapsulation** | Domain classes | Private fields, getters/setters |
| **Inheritance** | Person → Student/Instructor | Class inheritance with super |
| **Abstraction** | Person.java | Abstract class and methods |
| **Polymorphism** | Person.toString() | Method overriding and virtual calls |
| **Access Levels** | All classes | private, protected, public usage |
| **Interfaces** | Persistable, Searchable | Interface definition and implementation |
| **Enums** | Semester, Grade | Enum with constructors and methods |
| **Lambda Expressions** | Service classes | Functional programming |
| **Stream API** | Service classes | Data processing and filtering |
| **Date/Time API** | All classes | LocalDate, LocalDateTime usage |
| **NIO.2** | ImportExportService, BackupService | File operations with Path and Files |
| **Exception Handling** | All classes | try/catch, custom exceptions |
| **Design Patterns** | AppConfig, Course | Singleton and Builder patterns |
| **Generics** | Searchable<T> | Generic interface implementation |
| **Collections** | Service classes | List, Map, Set usage |
| **Recursion** | BackupService | Recursive file operations |

## Usage Examples

### 1. Adding a Student
```
1. Manage Students
2. Add Student
Enter Student ID: STU001
Enter Registration Number: 2023001
Enter Full Name: John Smith
Enter Email: john.smith@university.edu
Enter Date of Birth: 2000-05-15
Enter Department: Computer Science
Enter Current Semester: 3
```

### 2. Creating a Course
```
2. Manage Courses
1. Add Course
Enter Course Code: CS101
Enter Course Title: Introduction to Programming
Enter Credits: 3
Enter Instructor ID: INST001
Enter Semester: SPRING
Enter Department: Computer Science
Enter Max Enrollment: 30
```

### 3. Enrolling a Student
```
3. Manage Enrollments
1. Enroll Student
Enter Student ID: STU001
Enter Course Code: CS101
```

### 4. Recording Grades
```
4. Manage Grades
1. Record Grade
Enter Student ID: STU001
Enter Course Code: CS101
Enter Percentage Score: 85.5
```

### 5. Generating Reports
```
7. Generate Reports
1. GPA Report
```

### 6. Importing Data
```
5. Import/Export Data
1. Import Students from CSV
Enter CSV file path: test-data/students.csv
```

### 7. Creating Backups
```
6. Backup Operations
1. Create Backup
```

## Screenshots

### Installation Verification
*Java version verification showing JDK 17 installation*
![Java Installation](screenshots/java-version.png)


### Project Structure
*CCRM project structure*

![Project Structure](screenshots/structure.png)


### Program Execution
*CCRM application running with main menu*

![Program Running](screenshots/program-running.png)


### Sample Operations
*Student management interface*

![Student Management](screenshots/student-management.png)


*Course management interface*

![Course Management](screenshots/course-management.png)


*Generated reports and statistics*

![Reports](screenshots/reports.png)


### File Operations
*Backup creation and management*

![Backup Operations](screenshots/backup-operations.png)


*Data export and import operations*

![Export Operations](screenshots/export-operations.png)


## Acknowledgments

- Java documentation and tutorials
- Eclipse IDE development team
- OpenJDK community
- Java programming community

---

**Note**: This project demonstrates comprehensive Java SE programming concepts and serves as an educational example of modern Java application development. All code is original and follows Java best practices and design patterns.
