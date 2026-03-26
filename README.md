🏦 Secure Banking Application (Java + MySQL)

📌 Project Overview

This is a console-based banking system developed using Java and MySQL.
It allows users to perform banking operations like account creation, login, deposit, withdrawal, and more with basic security features like OTP verification.

---

🚀 Features

👤 User Features

- Register new account
- Secure login with PIN
- Deposit money
- Withdraw money
- Check account balance
- View mini statement
- Transfer money
- Change PIN
- Forgot PIN (with OTP verification)

🔐 Security Features

- OTP verification for sensitive operations
- Input validation (email, phone, PIN)
- Limited login attempts

👨‍💼 Admin Features

- View all accounts
- Delete account (soft delete)
- Check total bank balance

---

🛠️ Technologies Used

- Java (JDK 8 or above)
- MySQL Database
- JDBC (Java Database Connectivity)

---

🗂️ Project Structure

BankProject/
│
├── BankApp.java          # Main class (Entry point)
├── BankService.java      # Business logic
├── DBConnection.java     # Database connection
├── OTPUtil.java          # OTP generation
├── ValidationUtil.java   # Input validation
└── mysql-connector.jar   # MySQL JDBC Driver

---

⚙️ Setup Instructions

🔹 1. Install Requirements

- Install Java (JDK)
- Install MySQL Server

---

🔹 2. Start MySQL Server

Make sure MySQL is running before executing the program.

---

🔹 3. Create Database and Tables

Run the following SQL commands:

CREATE DATABASE bankdb;
USE bankdb;

CREATE TABLE accounts (
    acc_no BIGINT PRIMARY KEY,
    name VARCHAR(50),
    email VARCHAR(100),
    phone VARCHAR(15),
    pin INT,
    balance DOUBLE,
    active BOOLEAN DEFAULT TRUE
);

CREATE TABLE transactions (
    tx_id INT AUTO_INCREMENT PRIMARY KEY,
    acc_no BIGINT,
    tx_type VARCHAR(30),
    amount DOUBLE,
    description VARCHAR(100),
    tx_time TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

---

🔹 4. Update Database Credentials

Open "DBConnection.java" and update:

private static final String USER = "root";
private static final String PASSWORD = "your_password";

---

🔹 5. Compile the Project

Open Command Prompt inside project folder and run:

javac *.java

---

🔹 6. Run the Application

java BankApp

---

📋 Usage

1. Register a new account
2. Login using account number and PIN
3. Perform banking operations
4. Admin can login using:
   - ID: "admin"
   - Password: "1234"

---

⚠️ Notes

- Ensure MySQL server is running before execution
- All Java files must be in the same folder
- MySQL Connector JAR must be included if needed
- OTP is simulated (displayed in console)

---

🎯 Future Enhancements

- GUI using JavaFX or Swing
- Email/SMS OTP integration
- Transaction history export
- Password encryption

---

👨‍💻 Author

Developed as a mini project for learning Java + MySQL integration.

---
