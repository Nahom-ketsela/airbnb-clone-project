# The Airbnb Clone Project 

## Project Overview
Backend application that simulates a booking platform like Airbnb. The goal is to practice backend architecture, API design, database modeling, security, and CI/CD in a collaborative setup.

## Team Roles
- Backend Developer - builds API endpoints, models, and business rules, and writes tests.  
- Database Administrator - designs and maintains the PostgreSQL schema, indexes, backups, and performance.  
- DevOps Engineer - sets up CI/CD, containerizes with Docker, and monitors deployments.  
- QA Engineer - creates test plans, runs automated and manual tests, and tracks defects.  

## Technology Stack
- Django and Django REST Framework - core backend and REST APIs.  
- GraphQL - flexible querying for clients where needed.  
- PostgreSQL - primary relational database.  
- Celery and Redis - background tasks and caching.  
- Docker - consistent local and CI environments.  
- GitHub Actions - automated CI and optional CD.  

## Database Design
### Users
Fields: id, username, email, password, is_host  
Relations: one user can create many properties, make many bookings, and write many reviews.  

### Properties
Fields: id, title, description, price_per_night, host  
Relations: property belongs to one host, has many bookings and reviews.  

### Bookings
Fields: id, user_id, property_id, check_in, check_out, status  
Relations: booking belongs to a user and a property.  

### Reviews
Fields: id, property_id, user_id, rating, comment  
Relations: review belongs to a user and a property.  

### Payments
Fields: id, booking_id, amount, status, method  
Relations: payment belongs to a booking.  

## Feature Breakdown
- User management - registration, login, profile.  
- Property management - create and update listings and photos.  
- Booking system - availability checks and reservations.  
- Payments - create and track payment records and outcomes.  
- Reviews - guests rate and comment after stays.  

## API Security
- Authentication - JWT or session tokens with secure handling.  
- Authorization - role and object level checks.  
- Rate limiting - protect login and other sensitive endpoints.  
- Data protection - password hashing and HTTPS.  
- Input validation and safe error handling - prevent common web risks and avoid leaking internals.  

## CI/CD Pipeline
- Definition - automated build, test, and deploy.  
- Purpose - fast feedback and reliable releases for auth, bookings, and payments.  
- Tools - GitHub Actions for workflows, Docker for consistent environments.  
