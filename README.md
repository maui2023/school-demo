# school-demo

A smart school management system built with **PHP 8.4**, **MariaDB**, and **Bootstrap 5**.  
This system is designed to efficiently manage students, classes, and teacher roles with fine-grained access control.

## Features

- **Role-based Access Control** for teachers and students
- **Class and Student Management**
- **Timetable Viewing** for students
- **Modern UI** with Bootstrap 5
- **Extensible Architecture** using PHP interfaces and OOP best practices

## User Roles & Permissions

| Role                | View | Edit | Comment | Move Students | Accept Moves | Syllabus Edit | Scope                  |
|---------------------|------|------|---------|---------------|--------------|---------------|------------------------|
| Head Teacher        | ✔️   |      | ✔️      |               |              |               | All classes            |
| Vice Head Teacher   | ✔️   | ✔️   | ✔️      | ✔️            | ✔️           | ✔️            | All classes            |
| Class Teacher       | ✔️   |      |         | ✔️ (own class) | ✔️ (own class)| ✔️ (if also syllabus teacher) | Own class only         |
| Syllabus Teacher    | ✔️   |      |         |               |              | ✔️            | Own subject/class only |
| Student             | ✔️   |      |         |               |              |               | Own class timetable    |

- **Teachers can be reassigned to different roles at any time.**
- **Syllabus teachers can only edit their assigned subject in a class.**
- **Class teachers can also be syllabus teachers for their class.**

## Technical Stack

- **Backend:** PHP 8.4 (OOP, Interfaces)  
  - See [PHP Interfaces](https://www.php.net/manual/en/language.oop5.interfaces.php)
- **Database:** MariaDB
- **Frontend:** Bootstrap 5

## Architecture Overview

- **OOP Principles:**  
  Use PHP interfaces to define contracts for user roles and permissions, making the system extensible and maintainable.
- **Database Design:**  
  Normalize tables for users, roles, classes, students, subjects, and timetables.
- **UI/UX:**  
  Responsive design with Bootstrap 5 for a modern, accessible interface.

## Suggestions & Best Practices

- **Implement unit tests** for business logic (e.g., role permissions).
- **Use migrations** for database schema management.
- **Document code** and maintain clear API endpoints.
- **Consider using Composer** for dependency management.
- **Plan for localization** if supporting multiple languages.

## Getting Started

1. **Clone the repository**
    ```bash
    git clone https://github.com/yourusername/school-demo.git
    ```
2. **Install dependencies**
    ```bash
    composer install
    ```
3. **Configure environment**
    - Copy `.env.example` to `.env` and set your database credentials.
4. **Run migrations**
    ```bash
    php artisan migrate
    ```
5. **Serve the application**
    ```bash
    php -S localhost:8000 -t public
    ```

## License

MIT License

---

*Built with ❤️ using PHP, MariaDB, and Bootstrap 5.*
