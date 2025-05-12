# airbnb-clone-project
# Airbnb Clone Project

## Overview

This project is a clone of the core functionality of Airbnb, designed to facilitate listing properties, managing bookings, and handling payments through a responsive web application. It allows users to register, log in, book properties, and leave reviews. The project follows modern web development practices using a full-stack approach.

---

## Team Roles

- **Backend Developer**: Responsible for creating and maintaining server-side logic, APIs, and integrations. Works primarily with Django and Django REST Framework.

- **Frontend Developer**: Focuses on the user interface and user experience using technologies like React or HTML/CSS/JavaScript.

- **Database Administrator (DBA)**: Manages the PostgreSQL database, ensures data consistency, security, and optimizes queries.

- **DevOps Engineer**: Sets up CI/CD pipelines, deployment environments, and manages infrastructure using Docker and GitHub Actions.

- **Project Manager**: Coordinates the team, tracks progress, and ensures deadlines and quality standards are met.

---

## Technology Stack

- **Django**: A Python-based web framework used for building the backend and APIs.

- **Django REST Framework (DRF)**: Provides tools for building RESTful APIs efficiently and securely.

- **PostgreSQL**: A powerful, open-source object-relational database system to store structured project data.

- **GraphQL (optional)**: For more flexible API queries and mutations if added alongside REST.

- **React (optional)**: For building the interactive frontend.

- **Docker**: Containerizes the application for consistent development, testing, and deployment environments.

- **GitHub Actions**: Automates testing and deployment workflows as part of the CI/CD pipeline.

---

## Database Design

Key Entities and Fields:

- **User**
  - id (Primary Key)
  - name
  - email
  - password
  - role (host/guest)

- **Property**
  - id (Primary Key)
  - title
  - description
  - price_per_night
  - location
  - owner (Foreign Key → User)

- **Booking**
  - id (Primary Key)
  - user (Foreign Key → User)
  - property (Foreign Key → Property)
  - start_date
  - end_date
  - total_price

- **Review**
  - id (Primary Key)
  - user (Foreign Key → User)
  - property (Foreign Key → Property)
  - rating
  - comment

- **Payment**
  - id (Primary Key)
  - booking (Foreign Key → Booking)
  - amount
  - status
  - timestamp

### Relationships:
- A user can have many properties.
- A booking is linked to one user and one property.
- A review belongs to one user and one property.
- A payment is tied to a booking.

---

## Feature Breakdown

- **User Management**
  - Users can register, log in, update profiles, and manage roles (host/guest).
  - Authentication is handled securely using JWT or session-based auth.

- **Property Management**
  - Hosts can list new properties with images, pricing, and availability.
  - Guests can view, filter, and search listings.

- **Booking System**
  - Guests can book properties for specific dates.
  - Hosts can approve or reject bookings.

- **Reviews**
  - Guests can leave reviews after completing a booking.
  - Properties display average ratings and user comments.

- **Payments**
  - Integration with payment gateway (like Stripe or Paystack) to handle bookings.
  - Payment status updates are tracked for each booking.

---

## API Security

Key Security Measures:

- **Authentication**: Users must log in before accessing protected endpoints. JWT (JSON Web Tokens) or Django session auth is used.

- **Authorization**: Only property owners can modify or delete their listings; only guests can create bookings.

- **Rate Limiting**: Prevents abuse of the API (e.g., login attempts, spamming reviews).

- **Input Validation**: Ensures all data submitted to the backend is clean and prevents injection attacks.

**Why it matters:**

- Protects sensitive user data like passwords and payment info.
- Prevents unauthorized access to properties or bookings.
- Ensures the integrity of the booking and review systems.

---

## CI/CD Pipeline

- **CI/CD (Continuous Integration/Continuous Deployment)**: Automates the testing and deployment of the application to avoid manual errors and save time.

- **Why it’s important**:
  - Ensures code quality by running tests on every push.
  - Automatically deploys working code to staging or production.

- **Tools Used**:
  - **GitHub Actions**: Automates workflows such as testing, linting, and deployment.
  - **Docker**: Creates reproducible containers for development and deployment environments.


