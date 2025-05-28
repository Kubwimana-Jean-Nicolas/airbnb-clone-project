# Airbnb Clone Project

## 🚀 Overview

The Airbnb Clone Project is a backend system that replicates core features of Airbnb, focusing on user interactions, property listings, bookings, payments, and reviews. It is designed to be scalable, maintainable, and optimized for real-world performance.

## 🎯 Project Goals

- **User Management**: Secure registration, authentication, and profile updates.
- **Property Management**: CRUD operations for property listings.
- **Booking System**: Booking creation, updates, and cancellations.
- **Payment Processing**: Integration for secure payment handling.
- **Review System**: User reviews and ratings for properties.
- **Data Optimization**: Efficient storage and fast data retrieval.

## 🛠️ Technology Stack

- **Django**: Web framework for the backend
- **Django REST Framework**: RESTful API development
- **PostgreSQL**: Relational database for data storage
- **GraphQL**: Flexible data querying
- **Celery**: Task queue for asynchronous operations
- **Redis**: Caching and session management
- **Docker**: Containerization and deployment
- **CI/CD**: Automated testing and deployment

## 📌 API Highlights

- **Users**: Register, authenticate, update, and delete
- **Properties**: CRUD for property listings
- **Bookings**: Manage property reservations
- **Payments**: Handle payment processing
- **Reviews**: Post and manage property reviews

---

## 📂 Status

Project setup initialized. Development in progress.


## 👥 Team Roles

The success of the Airbnb Clone backend relies on the collaboration of different roles, each with specialized responsibilities:

### 🧑‍💻 Backend Developer
- **Responsibilities**: 
  - Implement API endpoints for users, properties, bookings, payments, and reviews.
  - Write business logic and manage integrations like Celery, Redis, and GraphQL.
  - Ensure security, scalability, and maintainability of the backend system.

### 🗃️ Database Administrator (DBA)
- **Responsibilities**:
  - Design and maintain the PostgreSQL database schema.
  - Implement indexing and database optimization for fast queries.
  - Monitor data integrity, backups, and performance tuning.

### ⚙️ DevOps Engineer
- **Responsibilities**:
  - Set up and manage CI/CD pipelines for automated testing and deployment.
  - Containerize the backend using Docker.
  - Monitor the application and ensure high availability in production.

### 🧪 QA Engineer
- **Responsibilities**:
  - Write and execute test cases for API functionality.
  - Perform integration and regression testing.
  - Report bugs and ensure features meet quality standards before deployment.

## 🗄️ Database Design

The Airbnb Clone backend requires a well-structured relational database. Below are the key entities and their relationships:

### 👤 Users
**Fields:**
- `id`: Unique identifier for each user
- `name`: Full name of the user
- `email`: User's email address (unique)
- `password`: Hashed password for authentication
- `role`: Indicates whether the user is a host or guest

**Relationships:**
- A user can **own multiple properties**
- A user can **create multiple bookings**
- A user can **write multiple reviews**

---

### 🏠 Properties
**Fields:**
- `id`: Unique identifier for each property
- `title`: Name of the listing
- `description`: Detailed information about the property
- `location`: Address or city of the property
- `host_id`: Foreign key linked to the user (host)

**Relationships:**
- A property is **owned by one user**
- A property can have **many bookings**
- A property can have **many reviews**

---

### 📅 Bookings
**Fields:**
- `id`: Unique identifier for each booking
- `user_id`: Foreign key linked to the user (guest)
- `property_id`: Foreign key linked to the booked property
- `check_in`: Date of check-in
- `check_out`: Date of check-out

**Relationships:**
- A booking is **made by one user** for **one property**
- A booking can be **linked to a payment**

---

### 💳 Payments
**Fields:**
- `id`: Unique identifier for the payment
- `booking_id`: Foreign key linked to the booking
- `amount`: Total payment amount
- `status`: Status of the payment (e.g., paid, pending)
- `payment_date`: Date of transaction

**Relationships:**
- A payment is **linked to one booking**

---

### 📝 Reviews
**Fields:**
- `id`: Unique identifier for each review
- `user_id`: Foreign key of the user who posted the review
- `property_id`: Foreign key of the reviewed property
- `rating`: Numeric rating (e.g., 1 to 5)
- `comment`: Text feedback about the property

**Relationships:**
- A review is **posted by one user**
- A review is **about one property**


