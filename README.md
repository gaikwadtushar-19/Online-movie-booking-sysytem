# 🎬 Movie Booking System – SQL Project

## Overview
The **Movie Booking System** is a relational database project designed to simulate an online movie ticket booking platform.  
It manages **users, movies, theatres, shows, seats, bookings, payments, and reviews** with proper relational integrity and constraints.

This project demonstrates database concepts like **table creation, relationships, foreign keys, data insertion, and query management**.

---

## Features
- **User Management** – Stores user registration details.  
- **Movie Management** – Stores movie details including genre, language, duration, and release date.  
- **Theatre & Show Management** – Schedules movies in different theatres with pricing.  
- **Seat Allocation** – Tracks seat availability and booking.  
- **Bookings & Payments** – Records user bookings and payment status.  
- **Reviews** – Collects user ratings and feedback.  

---

## Database Schema Overview
The database contains the following entities:

1. **Users** – Customer information.  
2. **Movies** – Movie details.  
3. **Theatres** – Theatre information.  
4. **Shows** – Movie shows in theatres.  
5. **Seats** – Seats per screen and type (Regular / Premium).  
6. **Bookings** – Ticket booking records.  
7. **Booking_Seats** – Seat allocation per booking.  
8. **Payments** – Tracks payment method and status.  
9. **Reviews** – User ratings and comments.  

**Relationships:**
- A user can make multiple bookings.  
- A movie can have multiple shows in different theatres.  
- Each booking can include multiple seats.  
- Each booking has a corresponding payment.  
- A user can submit reviews for multiple movies.  


```bash
git clone https://github.com/your-username/movie-booking-system.git
