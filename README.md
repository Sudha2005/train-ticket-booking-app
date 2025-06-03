# train-ticket-booking-app
A Train Ticket Booking App System project for Database Management Course.

## 📚 Abstract

The Train Ticket Booking App is a mobile application that provides a user-friendly platform for booking train tickets. It includes features like:
- Real-time train schedules
- Seat availability
- Booking management
- Secure payments via card/UPI/wallet
- Multilingual support
- PNR status tracking and more

The system integrates a secure backend database with a front-end built using **Python (Tkinter)** and **MySQL**.

---

## ⚙️ Technologies Used

- Python (Tkinter)
- MySQL
- SQL
- API integration (future enhancement)

## 🧾 SQL Sample

```sql
CREATE DATABASE train_booking;
USE train_booking;

CREATE TABLE users (
  username VARCHAR(100) PRIMARY KEY,
  password VARCHAR(100) NOT NULL
);

CREATE TABLE trains (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100),
  source VARCHAR(100),
  destination VARCHAR(100),
  travel_date DATE,
  available_seats INT,
  price INT
);

CREATE TABLE bookings (
  id INT AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(100),
  train_id INT,
  seats INT,
  total INT,
  FOREIGN KEY (username) REFERENCES users(username),
  FOREIGN KEY (train_id) REFERENCES trains(id)
);
