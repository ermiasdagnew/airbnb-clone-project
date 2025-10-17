# Airbnb Clone Project

## Overview
The Airbnb Clone backend project simulates a booking platform where users can register, list properties, make bookings, process payments, and leave reviews. The project aims to build a scalable, secure, and well-documented backend system.

## Project Goals
- User Management
- Property Management
- Booking System
- Payment Processing
- Review System
- Database Optimization

## Tech Stack
- Django & Django REST Framework
- PostgreSQL or MySQL
- GraphQL
- Celery
- Redis
- Docker
- CI/CD Pipelines
Team Roles
## Team Roles

### Backend Developer
Responsible for implementing API endpoints, server-side logic, and database interactions to ensure the backend works correctly.

### Database Administrator (DBA)
Manages the database design, indexing, and optimization to ensure efficient and secure data storage.

### DevOps Engineer
Handles deployment, server configuration, monitoring, and CI/CD pipelines to ensure smooth and reliable application delivery.

### QA Engineer
Tests backend functionalities, identifies bugs, and ensures that features work as expected before release.
Technology Stack
## Technology Stack

### 1. Python
The core programming language used to develop the backend logic and manage data flow between the database and the user interface.

### 2. Django
A powerful Python web framework used to build scalable backend services and RESTful APIs quickly and securely.

### 3. PostgreSQL
A relational database system used to store and manage user, property, and booking data efficiently.

### 4. HTML/CSS
Used to structure and style the web pages for the user interface, ensuring a clean and responsive design.

### 5. JavaScript
Adds interactivity and dynamic behavior to the frontend, improving the user experience.

### 6. Git & GitHub
Used for version control, allowing team members to collaborate and track changes to the project codebase.

### 7. Docker (optional)
Used to containerize the application, ensuring consistent environments across development and production.

### 8. REST API
Defines how frontend and backend communicate securely and efficiently.
## Database Design

The database for the Airbnb Clone project is designed to manage users, properties, bookings, payments, and reviews. It follows a relational structure to ensure data integrity and efficient querying.

### **Entities and Their Fields**

#### 1. Users
- **id**: unique identifier for each user  
- **name**: full name of the user  
- **email**: user’s email address (must be unique)  
- **password**: hashed password for security  
- **role**: defines if the user is a host or guest  

#### 2. Properties
- **id**: unique identifier for each property  
- **title**: short name or title of the listing  
- **description**: detailed information about the property  
- **location**: city or area where the property is located  
- **price_per_night**: rental cost per night  
- **host_id**: references the user who owns the property  

#### 3. Bookings
- **id**: unique identifier for each booking  
- **user_id**: references the user making the booking  
- **property_id**: references the booked property  
- **check_in**: start date of the stay  
- **check_out**: end date of the stay  
- **status**: booking status (e.g., confirmed, cancelled)  

#### 4. Payments
- **id**: unique identifier for each payment  
- **booking_id**: references the related booking  
- **amount**: total amount paid  
- **payment_date**: date of payment  
- **payment_method**: e.g., credit card, PayPal  

#### 5. Reviews
- **id**: unique identifier for each review  
- **user_id**: references the user who wrote the review  
- **property_id**: references the reviewed property  
- **rating**: numerical rating (1–5 stars)  
- **comment**: optional text feedback  

---

### **Entity Relationships**

- A **User** can list **multiple Properties** (1-to-many).  
- A **Property** can have **many Bookings** (1-to-many).  
- A **Booking** is associated with **one Payment** (1-to-1).  
- A **User** can make **many Bookings** (1-to-many).  
- A **Property** can have **many Reviews**, and a **User** can write **many Reviews** (many-to-many relationship handled through the Reviews table).

---

### **Example Schema Diagram (Conceptually)**

User (1) ——< Property (many)
User (1) ——< Booking (many)
Booking (1) ——1 Payment
Property (1) ——< Review (many)
User (1) ——< Review (many)
