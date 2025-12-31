
# PHP User Management System

This project is a simple **PHP user management system** using **PDO** and the **Singleton pattern** for database connection. It allows you to create users, authenticate them, search users, and update user data.

---

## Features

* Singleton database connection (PDO)
* User registration (signup)
* User authentication (signin)
* Search users by name
* Update user information
* Secure password hashing (bcrypt)

---

## Requirements

* PHP 8.0 or higher
* MySQL
* PDO extension enabled

---

## Database Setup

Create a database named:

```sql
live_coding_db
```

Create the `users` table:

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nom VARCHAR(100),
    prenom VARCHAR(100),
    email VARCHAR(150) UNIQUE,
    password VARCHAR(255)
);
```

---

## Configuration

Update database credentials in the `Database` class if needed:

```php
mysql:host=localhost;dbname=live_coding_db
username: root
password: Sa@123456
```

---

## Usage Examples

### Signup (Create User)

```php
User::signup("Omar", "El Amrani", "omar@gmail.com", "password123");
```

### Signin (Login)

```php
$user = User::signin("omar@gmail.com", "password123");
echo $user;
```

### Find User by Email

```php
$user = User::findByEmail("omar@gmail.com");
```

### Search Users by Name

```php
$users = User::searchByName("Omar");
```

### Update User

```php
$user->setNom("NewName");
$user->save();
```

---

## Security

* Passwords are hashed using `password_hash()`
* Authentication uses `password_verify()`
* Prepared statements protect against SQL injection

---

Simple PHP project for learning **OOP**, **PDO**, and **Authentication** concepts.


