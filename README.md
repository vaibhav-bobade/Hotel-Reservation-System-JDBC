# 🏨 Hotel Reservation System (JDBC & MySQL)

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white)
![JDBC](https://img.shields.io/badge/JDBC-Database_Connectivity-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)

A robust, menu-driven **Console-Based Hotel Reservation System** built using **Core Java** and **JDBC (Java Database Connectivity)** connected to a **MySQL** database.

This project demonstrates full CRUD (Create, Read, Update, Delete) operations on a relational database through an interactive CLI interface with formatted tabular output.

---

## 🚀 Features

- 📝 **Reserve a Room**: Register new guest details, room numbers, and contact numbers.
- 📋 **View All Reservations**: Display current reservation records formatted cleanly in ASCII tables.
- 🔍 **Search Room Number**: Lookup assigned room numbers using Reservation ID and Guest Name.
- ✏️ **Update Reservation**: Seamlessly modify existing reservation records.
- ❌ **Delete Reservation**: Cancel or remove existing reservations from the database.
- ⚡ **Graceful Exit**: Interactive console exit sequence.

---

## 🛠️ Tech Stack & Prerequisites

- **Programming Language**: Java (JDK 8 or higher)
- **Database**: MySQL Server (8.0+)
- **API**: JDBC (Java Database Connectivity)
- **Driver**: MySQL Connector/J (`mysql-connector-j-8.x.x.jar`)
- **IDE**: IntelliJ IDEA / Eclipse / VS Code (Optional)

---

## 🗄️ Database Setup

Before running the application, set up the MySQL database and table schema by executing the following SQL queries in **MySQL Workbench** or **MySQL Command Line Client**:

```sql
-- Create Database
CREATE DATABASE IF NOT EXISTS hotel_db;

-- Use Database
USE hotel_db;

-- Create Reservations Table
CREATE TABLE IF NOT EXISTS reservations (
    reservation_id INT AUTO_INCREMENT PRIMARY KEY,
    guest_name VARCHAR(255) NOT NULL,
    room_number INT NOT NULL,
    contact_number VARCHAR(20) NOT NULL,
    reservation_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

## ⚙️ Configuration

1. Open `src/HotelReservationSystem.java`.
2. Update the MySQL database credentials (`url`, `username`, `password`) according to your local environment:

```java
private static final String url = "jdbc:mysql://localhost:3306/hotel_db";
private static final String username = "root";
private static final String password = "YOUR_MYSQL_PASSWORD";
```

---

## 📥 How to Run

### Method 1: Via IntelliJ IDEA (Recommended)
1. Open the project in **IntelliJ IDEA**.
2. Ensure **MySQL Connector/J JAR** library is added to your project dependencies:
   - Go to `File` ➔ `Project Structure` ➔ `Libraries`.
   - Click `+` ➔ select `Java` ➔ browse and select your `mysql-connector-j-8.x.x.jar`.
3. Open `src/HotelReservationSystem.java` and click **Run**.

### Method 2: Via Terminal / Command Line
1. Compile the code with the MySQL connector in your classpath:
   ```bash
   javac -cp "path/to/mysql-connector-j-8.x.x.jar" src/HotelReservationSystem.java -d bin/
   ```
2. Run the application:
   ```bash
   java -cp "bin;path/to/mysql-connector-j-8.x.x.jar" HotelReservationSystem
   ```

---

## 🖥️ Console Output Preview

```text
HOTEL MANAGEMENT SYSTEM
1. Reserve a room
2. View Reservations
3. Get Room Number
4. Update Reservations
5. Delete Reservations
0. Exit
Choose an option: 2

Current Reservations:
+----------------+-----------------+---------------+----------------------+-------------------------+
| Reservation ID | Guest           | Room Number   | Contact Number      | Reservation Date        |
+----------------+-----------------+---------------+----------------------+-------------------------+
| 1              | John Doe        | 101           | 9876543210           | 2026-10-05 16:00:00     |
+----------------+-----------------+---------------+----------------------+-------------------------+
```

---

## 📁 Project Structure

```text
Hotel-Reservation-System-JDBC/
├── src/
│   └── HotelReservationSystem.java   # Main application source code
├── .gitignore                         # Git ignore configuration
├── Hotel Reservation System JDBC Project.iml
└── README.md                          # Project documentation
```

---

## 🤝 Contributing

Contributions are welcome! Feel free to fork this repository, submit issues, or create pull requests for enhancements (such as adding `PreparedStatement` to prevent SQL injection or building a GUI).

---

## 📜 License

This project is open-source and available under the [MIT License](LICENSE).
