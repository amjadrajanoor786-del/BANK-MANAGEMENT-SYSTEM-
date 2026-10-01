# 🏦 Bank Management System

This is a Java-based Bank Management System project with a simple GUI using **Swing** and database connectivity using **MySQL**. It supports user signup, login, deposit, withdrawal, and balance inquiry functionalities.

---

## 📋 Features

- ✅ User Signup
- ✅ Login Authentication
- 💰 Deposit and Withdraw
- 🧾 Balance Enquiry
- 🗃️ Transaction Management via MySQL
- 🔐 Password and PIN-based security
- 📊 Simple GUI using Java Swing

---

## 🧰 Technologies Used

- Java (JDK 8+)
- Swing (Java GUI Framework)
- JDBC (Java Database Connectivity)
- MySQL (Database)

---

## 📦 Project Structure

```bash
Bank-Management-System/
│
├── src/
│   ├── Login.java
│   ├── Signup.java
│   ├── Deposit.java
│   ├── Withdrawl.java
│   ├── BalanceEnquiry.java
│   ├── Connn.java
│   └── main_Class.java
│
├── database/
│   └── bank.sql
│
└── README.md
```

---

## 🛠️ Requirements

Before running the project, ensure you have the following installed:

- ✅ Java Development Kit (JDK) 8 or above
- ✅ MySQL Server (5.x or 8.x)
- ✅ MySQL Connector/J (JDBC driver)
- ✅ IDE like Eclipse, IntelliJ, or NetBeans

---

## 🗃️ Database Setup

1. Open MySQL Command Line or MySQL Workbench.
2. Run the following SQL commands to create the database and tables:

```sql
CREATE DATABASE bankdb;
USE bankdb;

CREATE TABLE users (
    accountNo INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    dob DATE,
    gender VARCHAR(10),
    email VARCHAR(100),
    phone VARCHAR(15),
    address TEXT,
    pin INT
);

CREATE TABLE transactions (
    txnID INT PRIMARY KEY AUTO_INCREMENT,
    accountNo INT,
    date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    type VARCHAR(20),
    amount DECIMAL(10,2),
    FOREIGN KEY (accountNo) REFERENCES users(accountNo)
);
```

---

## 🔌 How to Run the Project

1. **Clone or download** this repository.
2. **Import the project** into your Java IDE (like IntelliJ or Eclipse).
3. Add **MySQL Connector/J JAR file** to your project’s build path.
4. Update the MySQL **connection details** in `Connn.java`:

```java
String url = "jdbc:mysql://localhost:3306/bankSystem";
String user = "root";
String password = "AyushVish";
```

5. Compile and run `main_Class.java`.

---

## 🧪 Test Accounts (Optional)

You can insert dummy data for testing:

```sql
INSERT INTO users (name, dob, gender, email, phone, address, pin)
VALUES ('Alice', '2000-05-25', 'Female', 'alice@example.com', '9876543210', 'Mumbai, India', 1234);
```

---

## 📌 Notes

- This is a **desktop application**.
- No internet connection is required once the database is set up locally.
- For production, consider encrypting passwords and securing database access.

---

## 📜 License

This project is for academic and educational purposes only.
