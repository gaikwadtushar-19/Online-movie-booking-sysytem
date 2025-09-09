create database movie_booking;
use movie_booking;
CREATE TABLE users (
    user_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    phone VARCHAR(15),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
INSERT INTO users (name, email, password, phone) VALUES
('Aarav', 'aarav@mail.com', 'pass1', '9876543201'),
('Vivaan', 'vivaan@mail.com', 'pass2', '9876543202'),
('Aditya', 'aditya@mail.com', 'pass3', '9876543203'),
('Krishna', 'krishna@mail.com', 'pass4', '9876543204'),
('Ishaan', 'ishaan@mail.com', 'pass5', '9876543205'),
('Anaya', 'anaya@mail.com', 'pass6', '9876543206'),
('Diya', 'diya@mail.com', 'pass7', '9876543207'),
('Ira', 'ira@mail.com', 'pass8', '9876543208'),
('Myra', 'myra@mail.com', 'pass9', '9876543209'),
('Aanya', 'aanya@mail.com', 'pass10', '9876543210');

CREATE TABLE movies (
    movie_id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(200) NOT NULL,
    genre VARCHAR(100),
    duration_in_hours decimal(5,2),
    language VARCHAR(50),
    release_date DATE,
    description TEXT
);

INSERT INTO movies (title, genre, duration_in_hours, language, release_date, description) VALUES
('Pathaan' , 'Action', 2.20, 'Hindi', '2023-01-25', 'A spy thriller starring Shah Rukh Khan'),
('Gully Boy ', 'Drama', 2.10, 'Hindi', '2019-02-14', 'A story of an underground rapper from Mumbai'),
('3 Idiots ', 'Comedy', 2.45, 'Hindi', '2009-12-25', 'An engineering student’s life journey'),
('Conjuring ', 'Horror', 1.50, 'English', '2013-07-19', 'Paranormal investigators help a family'),
('Andhadhun ', 'Thriller', 2.15, 'Hindi', '2018-10-05', 'A blind pianist becomes embroiled in murder'),
('La La Land ', 'Romance', 2.08, 'English', '2016-12-09', 'A jazz musician falls for an actress in LA'),
('Interstellar ', 'Sci-Fi', 2.49, 'English', '2014-11-07', 'Explorers travel through a wormhole in space'),
('Bahubali ', 'Adventure', 2.47, 'Telugu', '2015-07-10', 'An epic tale of kings and betrayal'),
('Harry Potter ', 'Fantasy', 2.30, 'English', '2001-11-16', 'A boy discovers he is a wizard'),
('Sherlock Holmes ', 'Mystery', 2.15, 'English', '2009-12-25', 'Detective Holmes solves crimes in London');


CREATE TABLE theatres (
    theatre_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    location VARCHAR(255),
    total_screens INT
);

INSERT INTO theatres (name, location, total_screens) VALUES
('INOX City Center', 'Pune', 5),
('PVR Phoenix', 'Mumbai', 7),
('Cinepolis', 'Delhi', 6),
('E-Square', 'Nagpur', 4),
('Carnival Cinemas', 'Nashik', 3),
('INOX Bund Garden', 'Pune', 5),
('PVR Orion', 'Bangalore', 6),
('Miraj Cinemas', 'Ahmedabad', 4),
('Wave Cinemas', 'Lucknow', 5),
('PVR Express', 'Hyderabad', 6);

CREATE TABLE shows (
    show_id INT AUTO_INCREMENT PRIMARY KEY,
    movie_id INT,
    theatre_id INT,
    show_time DATETIME,
    screen_no INT,
    price DECIMAL(8,2),
    FOREIGN KEY (movie_id) REFERENCES movies(movie_id),
    FOREIGN KEY (theatre_id) REFERENCES theatres(theatre_id)
);

INSERT INTO shows (movie_id, theatre_id, show_time, screen_no, price) VALUES
(1, 1, '2025-06-20 10:00:00', 1, 180.00),
(2, 2, '2025-06-20 13:00:00', 2, 200.00),
(3, 3, '2025-06-20 16:00:00', 3, 220.00),
(4, 4, '2025-06-21 10:30:00', 1, 190.00),
(5, 5, '2025-06-21 14:00:00', 2, 210.00),
(6, 6, '2025-06-21 17:00:00', 3, 230.00),
(7, 7, '2025-06-22 11:00:00', 1, 200.00),
(8, 8, '2025-06-22 15:00:00', 2, 180.00),
(9, 9, '2025-06-22 18:30:00', 3, 210.00),
(10, 10, '2025-06-23 12:00:00', 1, 220.00);

CREATE TABLE seats (
    seat_id INT AUTO_INCREMENT PRIMARY KEY,
    theatre_id INT,
    screen_no INT,
    seat_no VARCHAR(10),
    seat_type VARCHAR(50),
    FOREIGN KEY (theatre_id) REFERENCES theatres(theatre_id)
);

INSERT INTO seats (theatre_id, screen_no, seat_no, seat_type) VALUES
(1, 1, 'A1', 'Regular'),
(1, 1, 'A2', 'Regular'),
(1, 1, 'A3', 'Premium'),
(2, 2, 'B1', 'Regular'),
(2, 2, 'B2', 'Premium'),
(3, 3, 'C1', 'Regular'),
(3, 3, 'C2', 'Premium'),
(4, 1, 'D1', 'Regular'),
(4, 1, 'D2', 'Premium'),
(5, 2, 'E1', 'Regular');

CREATE TABLE bookings (
    booking_id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    show_id INT,
    booking_time TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    total_amount DECIMAL(10,2),
    status ENUM('CONFIRMED', 'CANCELLED') DEFAULT 'CONFIRMED',
    FOREIGN KEY (user_id) REFERENCES users(user_id),
    FOREIGN KEY (show_id) REFERENCES shows(show_id)
);

INSERT INTO bookings (user_id, show_id, total_amount, status) VALUES
(1, 1, 360.00, 'CONFIRMED'),
(2, 2, 200.00, 'CONFIRMED'),
(3, 3, 220.00, 'CONFIRMED'),
(4, 4, 190.00, 'CANCELLED'),
(5, 5, 210.00, 'CONFIRMED'),
(6, 6, 460.00, 'CONFIRMED'),
(7, 7, 200.00, 'CONFIRMED'),
(8, 8, 180.00, 'CONFIRMED'),
(9, 9, 210.00, 'CANCELLED'),
(10, 10, 220.00, 'CONFIRMED');

CREATE TABLE booking_seats (
    booking_seat_id INT AUTO_INCREMENT PRIMARY KEY,
    booking_id INT,
    seat_number VARCHAR(10),
    FOREIGN KEY (booking_id) REFERENCES bookings(booking_id)
);
INSERT INTO booking_seats (booking_id, seat_number) VALUES
(1, 'H25'),
(2, 'K8'),
(3, 'J24'),
(4, 'E1'),
(5, 'X13'),
(6, 'F16'),
(7, 'R3'),
(8, 'I29'),
(9, 'L19'),
(10, 'B17');

CREATE TABLE payments (
    payment_id INT AUTO_INCREMENT PRIMARY KEY,
    booking_id INT,
    payment_method ENUM('CREDIT_CARD', 'DEBIT_CARD', 'UPI', 'NET_BANKING', 'WALLET') NOT NULL,
    amount_paid DECIMAL(10,2) NOT NULL,
    payment_status ENUM('SUCCESS', 'FAILED', 'PENDING') DEFAULT 'PENDING',
    payment_time TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (booking_id) REFERENCES bookings(booking_id)
);

INSERT INTO payments (booking_id, payment_method, amount_paid, payment_status) VALUES
(1, 'UPI', 360.00, 'SUCCESS'),
(2, 'CREDIT_CARD', 200.00, 'SUCCESS'),
(3, 'DEBIT_CARD', 220.00, 'SUCCESS'),
(4, 'NET_BANKING', 190.00, 'FAILED'),
(5, 'UPI', 210.00, 'SUCCESS'),
(6, 'UPI', 460.00, 'SUCCESS'),
(7, 'CREDIT_CARD', 200.00, 'SUCCESS'),
(8, 'WALLET', 180.00, 'SUCCESS'),
(9, 'UPI', 210.00, 'FAILED'),
(10, 'DEBIT_CARD', 220.00, 'SUCCESS');

CREATE TABLE reviews (
    review_id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    movie_id INT,
    rating INT CHECK (rating >= 1 AND rating <= 5),
    comment TEXT,
    review_time TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(user_id),
    FOREIGN KEY (movie_id) REFERENCES movies(movie_id)
);

INSERT INTO reviews (user_id, movie_id, rating, comment) VALUES
(1, 1, 4, 'Awesome movie!'),
(2, 2, 5, 'Loved the drama!'),
(3, 3, 3, 'Funny scenes'),
(4, 4, 4, 'Scary but fun'),
(5, 5, 5, 'Thrilling experience'),
(6, 6, 3, 'Good romantic story'),
(7, 7, 4, 'Amazing VFX'),
(8, 8, 5, 'Great adventure'),
(9, 9, 4, 'Fantastic world'),
(10, 10, 4, 'Mind-blowing mystery')  

-- all users
SELECT * FROM users;
 
-- List all movies with release year after 2020
SELECT title, genre, release_date FROM movies WHERE release_date > '2020-01-01';

-- Find all theatres in Pune
SELECT name, location  FROM theatres WHERE location = 'Pune';

-- Show bookings with user name and movie title
SELECT b.booking_id, u.name AS user_name, m.title AS movie_title, b.total_amount, b.status
FROM bookings b
JOIN users u ON b.user_id = u.user_id
JOIN shows s ON b.show_id = s.show_id
JOIN movies m ON s.movie_id = m.movie_id;

-- Show all shows for a given movie
SELECT m.title, t.name AS theatre_name, s.show_time, s.price
FROM shows s
JOIN movies m ON s.movie_id = m.movie_id
JOIN theatres t ON s.theatre_id = t.theatre_id
WHERE m.title = 'Pathaan';

-- Find seat details for a booking
SELECT b.booking_id, u.name, bs.seat_number
FROM booking_seats bs
JOIN bookings b ON bs.booking_id = b.booking_id
JOIN users u ON b.user_id = u.user_id
WHERE b.booking_id = 1;

-- Find total revenue from bookings
SELECT SUM(total_amount) AS total_revenue
FROM bookings
WHERE status = 'CONFIRMED';

-- Find average rating of each movie
SELECT m.title, AVG(r.rating) AS avg_rating
FROM reviews r
JOIN movies m ON r.movie_id = m.movie_id
GROUP BY m.title
ORDER BY avg_rating DESC;

-- Count number of bookings per user
SELECT u.name, COUNT(b.booking_id) AS total_bookings
FROM users u
JOIN bookings b ON u.user_id = b.user_id
GROUP BY u.user_id;

-- List users who booked but payment failed
SELECT u.name, b.booking_id, p.payment_status
FROM payments p
JOIN bookings b ON p.booking_id = b.booking_id
JOIN users u ON b.user_id = u.user_id
WHERE p.payment_status = 'FAILED';

-- Find most popular movie (by number of bookings)
SELECT m.title, COUNT(b.booking_id) AS total_bookings
FROM bookings b
JOIN shows s ON b.show_id = s.show_id
JOIN movies m ON s.movie_id = m.movie_id
WHERE b.status = 'CONFIRMED'
GROUP BY m.title
ORDER BY total_bookings DESC
LIMIT 1;

-- Find top 3 theatres with highest revenue
SELECT t.name, SUM(b.total_amount) AS total_revenue
FROM bookings b
JOIN shows s ON b.show_id = s.show_id
JOIN theatres t ON s.theatre_id = t.theatre_id
WHERE b.status = 'CONFIRMED'
GROUP BY t.name
ORDER BY total_revenue DESC
LIMIT 3;

-- Show seat availability per theatre screen (total vs booked)
SELECT t.name AS theatre, s.screen_no,
       COUNT(se.seat_id) AS total_seats,
       COUNT(bs.seat_number) AS booked_seats,
       (COUNT(se.seat_id) - COUNT(bs.seat_number)) AS available_seats
FROM seats se
JOIN theatres t ON se.theatre_id = t.theatre_id
LEFT JOIN shows s ON se.theatre_id = s.theatre_id AND se.screen_no = s.screen_no
LEFT JOIN bookings b ON s.show_id = b.show_id
LEFT JOIN booking_seats bs ON b.booking_id = bs.booking_id
GROUP BY t.name, s.screen_no;
