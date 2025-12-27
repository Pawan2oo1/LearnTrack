# LearnTrack – Student & Course Management System

LearnTrack is a menu-driven console application built with Core Java to manage students, courses, and enrollments. It is designed to practice OOP (interfaces, abstract classes, inheritance), collections (`ArrayList`), and basic application structure.

## Features

- **Student Management:** Create students, view all, search by ID, deactivate.
- **Course Management:** Create courses, view all courses.
- **Enrollment Management:** Enroll students in courses, view enrollments, update enrollment status.
- **Clean Architecture:** Separation between UI, services, entities, and utilities.
- **OOP Principles:** Interfaces, abstract classes, inheritance, encapsulation.

## Technology Stack

- **Language:** Java 25 LTS
- **IDE:** IntelliJ IDEA Community Edition
- **Build System:** IntelliJ default (no external build tool required)
- **Version Control:** Git & GitHub

## Project Structure

Base package: `com.airtribe.learntrack`

### Sub-Packages

```
src/
└── com/airtribe/learntrack/
    ├── entity/              (Person, Student, Course, Enrollment)
    ├── service/             (Service interfaces)
    ├── service/impl/        (ServiceImpl classes with ArrayList)
    ├── ui/                  (Main.java - console UI)
    └── util/                (IdGenerator, InputHelper)
```


## How to Run

### Using IntelliJ IDEA

1. Open the project in IntelliJ IDEA.
2. Ensure `src` folder is marked as **Sources Root**.
3. Navigate to `com.airtribe.learntrack.ui.Main`.
4. Click the green **Run** icon next to the `main` method.
5. Use the console menu to navigate through the application.

## Menu Structure

### Main Menu

```
=== LearnTrack Main Menu ===
1. Student Management
2. Course Management
3. Enrollment Management
0. Exit
```

### Student Management

- Add new student
- View all students
- Search student by ID
- Deactivate student

### Course Management

- Add new course
- View all courses

### Enrollment Management

- Enroll student to course
- View enrollments for a student
- Update enrollment status

### Static Members

**IdGenerator:**
- Uses static counters for generating unique IDs across the application.
- Ensures IDs are never duplicated.

**InputHelper:**
- Provides static methods for reading console input.

### Inheritance

`Person` is an abstract base class for all people in the system.

**Benefits:**
- Code reuse of common fields and methods.
- Easy to add more person types (e.g., `Trainer`, `Admin`).
- Polymorphism support through interfaces.

## Clean Code Practices

- **Small, focused methods:** Each method has a single responsibility.
- **Meaningful names:** Methods named after their behavior (e.g., `addStudent`, `findCourseById`).
- **Separation of concerns:** UI, services, and entities are in separate layers.
- **No try-catch:** Input validation uses helper functions and loops instead.

### Repository Structure

```
LearnTrack/
├── src/
│   └── com/airtribe/learntrack/
│       ├── entity/
│       │   ├── Person.java
│       │   ├── Student.java
│       │   ├── Course.java
│       │   ├── Enrollment.java
│       │   └── EnrollmentStatus.java
│       ├── service/
│       │   ├── StudentService.java
│       │   ├── CourseService.java
│       │   └── EnrollmentService.java
│       ├── service/impl/
│       │   ├── StudentServiceImpl.java
│       │   ├── CourseServiceImpl.java
│       │   └── EnrollmentServiceImpl.java
│       ├── ui/
│       │   └── Main.java
│       └── util/
│           ├── IdGenerator.java
│           └── InputHelper.java
├── docs/
│   ├── Setup_Instructions.md
│   ├── JVM_Basics.md
│   └── Design_Notes.md
├── README.md
└── .gitignore
```

## Future Enhancements

- Implement database connectivity using JDBC.
- Add user authentication and roles.

**Author:** Pawan Bhandari  
**Java Version:** Java 25 LTS  

