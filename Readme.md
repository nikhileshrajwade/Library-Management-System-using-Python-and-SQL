# Library Management System using Python and SQL

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![SQLite](https://img.shields.io/badge/SQLite-3-lightgrey)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Manipulation-orange)
![License: MIT](https://img.shields.io/badge/License-MIT-green)

## 📌 Project Overview
A robust, command-line Library Management System built to handle end-to-end daily library operations. Originally prototyped using flat `.xlsx` Excel files for storage, the backend has been completely refactored and upgraded to use a relational **SQLite database**. 

This system features role-based access control, automated fine calculations, real-time inventory tracking, and data visualization tools for administrative reporting.

## 🚀 Key Features

### 👤 User Module
* **Secure Login:** Authenticated access for registered students/users.
* **Book Issuing & Returning:** Users can search for books by ID or keyword and issue up to 3 books at a time.
* **Automated Fine Calculation:** The system automatically calculates fines (₹2 per day) for books kept beyond the 14-day limit using `pandas.Timestamp`.
* **Account Suspension:** Automatically suspends and removes users who accumulate a fine exceeding ₹500, moving them to an archived `removed_user` table.

### 🛡️ Admin Module
* **User Management:** Create new user accounts or manually delete existing ones.
* **Inventory Control:** Add new books, restock existing inventory, or remove discontinued books.
* **Data Visualization & Analytics:** Generates graphical reports using Matplotlib to display:
  * Ratio of available vs. issued books (Pie charts).
  * Inventory distribution by genre (Bar graphs).
  * Top 10 most expensive books in the library.
* **Overdue Management:** One-click functionality to review and purge overdue users from the active database.

## 🛠️ Technology Stack
* **Language:** Python 3
* **Database:** SQLite3 (Thread-safe configuration enabled)
* **Data Manipulation:** Pandas, NumPy
* **Data Visualization:** Matplotlib

## 🗄️ Database Schema
The backend operates on a single `library_management.db` SQLite database containing the following core tables:
1. `library_books`: Tracks Book ID, Title, Author, Category, Price, Total Copies, and Status.
2. `User_data`: Tracks User ID, Password, up to 3 Issued Books (with timestamps), and current Fine balance.
3. `Admin_data`: Stores secure Admin credentials.
4. `removed_user`: An archive table for users suspended due to massive overdue fines.

## ⚙️ Installation & Usage

### 1. Clone the Repository
```bash
git clone [https://github.com/your-username/Library_Management_System_using_Python_and_SQL.git](https://github.com/your-username/Library_Management_System_using_Python_and_SQL.git)
cd Library_Management_System_using_Python_and_SQL