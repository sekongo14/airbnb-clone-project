# airbnb-clone-project
airbnb-clone-project for alx courses

### About the Project
The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. It involves a deep dive into full-stack development, focusing on backend systems, database design, API development, and application security. This project enables learners to understand complex architectures, workflows, and collaborative team dynamics while building a scalable web application.

### Technology Stack

Django: A high-level Python web framework used for building the RESTful API.
Django REST Framework: Provides tools for creating and managing RESTful APIs.
PostgreSQL: A powerful relational database used for data storage.
GraphQL: Allows for flexible and efficient querying of data.
Celery: For handling asynchronous tasks such as sending notifications or processing payments.
Redis: Used for caching and session management.
Docker: Containerization tool for consistent development and deployment environments.
CI/CD Pipelines: Automated pipelines for testing and deploying code changes.

 ### Team Roles 👥

Backend Developer: Responsible for implementing API endpoints, database schemas, and business logic.
Database Administrator: Manages database design, indexing, and optimizations.
DevOps Engineer: Handles deployment, monitoring, and scaling of the backend services.
QA Engineer: Ensures the backend functionalities are thoroughly tested and meet quality standards.


👇

## Database Design
Key Entities

The main entities in the Airbnb project are:

Users

Properties

Bookings

Reviews

Payments

1. Users

Represents the people using the platform, including both hosts and guests.

Key Fields

id: Unique identifier for the user

name: Full name of the user

email: Email address (used for login)

role: Indicates whether the user is a Host or a Guest

created_at: Date the user registered

Relationships

A User (Host) can have multiple Properties.

A User (Guest) can make multiple Bookings and write Reviews.

2. Properties

Represents the accommodations listed on the platform.

Key Fields

id: Unique identifier for the property

title: Name or title of the property

description: Detailed description

price_per_night: Cost per night

host_id: Foreign key referencing the User (Host)

location: Address or city where the property is located

Relationships

A Property belongs to one Host (User).

A Property can have multiple Bookings and Reviews.

3. Bookings

Represents reservations made by guests for properties.

Key Fields

id: Unique identifier for the booking

property_id: Foreign key referencing the Property

guest_id: Foreign key referencing the User (Guest)

check_in: Date of arrival

check_out: Date of departure

status: Booking status (e.g., confirmed, cancelled, completed)

Relationships

A Booking belongs to one Property.

A Booking is made by one Guest (User).

A Booking can have one Payment.

4. Reviews

Represents feedback left by guests after their stay.

Key Fields

id: Unique identifier for the review

property_id: Foreign key referencing the Property

guest_id: Foreign key referencing the User (Guest)

rating: Numeric rating (1–5)

comment: Text feedback

created_at: Date the review was submitted

Relationships

A Review belongs to one Property.

A Review is written by one Guest (User).

5. Payments

Represents financial transactions related to bookings.

Key Fields

id: Unique identifier for the payment

booking_id: Foreign key referencing the Booking

amount: Total amount paid

payment_method: e.g., credit card, PayPal

status: Payment status (pending, completed, failed)

Relationships

A Payment belongs to one Booking.

Each Booking can have one Payment.

Entity Relationship Summary

A User (Host) ➜ can list many Properties

A User (Guest) ➜ can make many Bookings

A Property ➜ can have many Bookings and Reviews

A Booking ➜ belongs to one Property and one Guest

A Review ➜ belongs to one Property and one Guest

A Payment ➜ belongs to one Booking
