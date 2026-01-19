## EFREI Computer Science Assistant

### Project Overview

This project is a **web-based educational application** designed to help **EFREI students** improve their performance in computer science. It primarily targets **first-year students (L1)** and provides access to **previous continuous assessments (CAs)**, which usually take place every few weeks during the academic year.

---

## Table of Contents

* Project Context and Objectives
* Database Setup
* User Roles and Permissions
* Application Features
* Backend and Frontend Startup
* Additional Information

---

## Project Context

The application homepage displays the available computer science subjects, including:

* Python
* Data Structures
* Java
* C

By selecting a subject, students are redirected to a dedicated page where they can access multiple **continuous assessments (CAs)** related to that subject.

* Each subject initially includes **at least three assessments**
* Additional assessments can be added over time
* Assessments are presented as **multiple-choice quizzes**
* Answers are revealed at the end using the **“Check Answer”** feature

This system allows students to practice regularly and prepare effectively for exams.

---

## Database Configuration

* Create a **MySQL** database
* Configure the environment variables according to your database setup:

  * host
  * port
  * user
  * password
* Create the database and import the data using the **SQL_QUERY_DB** script

### Password Information

All passwords stored in the database are **encrypted**.
The actual password for all test accounts is:

**bbbb2005**

---

## Database Structure

The database contains two main tables:

### `users`

* `id` (primary key)
* `firstName`
* `lastName`
* `email`
* `password`
* `occupation` (defines access to modules)

### `subjects`

* `id` (primary key)
* `name`
* `active` (0 = inactive, 1 = active)

---

## User Roles

The application defines three user roles:

### EFREI Student

* Full access to all modules
* Access to all continuous assessments

### Student

* Access limited to the **Python** module only

### Administrator

* Full access to all modules
* Ability to enable or disable modules for all users

---

## Test Accounts

| Role          | Email                           | Password |
| ------------- | ------------------------------- | -------- |
| Administrator | [bot@ai.com](mailto:bot@ai.com) | bbbb2005 |
| EFREI Student | ***@mail.com                    | bbbb2005 |
| Student       | ***@mail.com                    | bbbb2005 |

---

## Application Features

* User authentication (sign-up and login)
* Role-based access control
* Interactive multiple-choice quizzes
* Answer validation via the **“Check Answer”** button
* User profile management:

  * First name
  * Last name
  * Occupation
  * Password
* **About** page explaining the purpose and scope of the project

---

## Backend and Frontend Launch

To start the application:

1. Navigate to the **server** directory
2. Run the following command:

```bash
npm run dev
```
