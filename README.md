# Bank-Management-System

# Bank Management System (Console Application)

This is a simple console-based Bank Management System built with Python and SQLAlchemy. It provides basic functionalities for user registration, login, account management (create, deposit, withdraw, transfer, view history), and administrative operations (manage users, view all accounts/transactions).

## Features

**User Operations:**
* **User Registration:** Create new user accounts.
* **User Login:** Securely log in with a username and password (hashed with `bcrypt`).
* **Account Creation:** Create savings or checking accounts linked to a user.
* **Deposit Funds:** Add money to an existing account.
* **Withdraw Funds:** Remove money from an account (with balance check).
* **Transfer Funds:** Transfer money between accounts within the system.
* **View Accounts:** List all bank accounts associated with the logged-in user.
* **View Transaction History:** See a detailed list of transactions for a specific account.

**Admin Operations:**
* **View All Users:** List all registered users in the system.
* **Toggle User Status:** Activate or deactivate user accounts.
* **View All Accounts:** See all bank accounts across all users.
* **View All Transactions:** Get a comprehensive list of all transactions in the system.
* **Search User:** Find users by username.

## Technologies Used

* **Python 3.x:** The core programming language.
* **SQLAlchemy:** Python SQL Toolkit and Object Relational Mapper for database interactions.
* **SQLite:** Default database for simplicity (`bank.db`). Can be configured for other databases.
* **Bcrypt:** For secure password hashing.

## Setup and Installation

Follow these steps to set up and run the Bank Management System on your local machine.

### 1. Prerequisites

* Python 3.7 or higher installed.

### 2. Clone the Repository (or copy the file)

If you've successfully uploaded the file to GitHub, you can clone your repository. Otherwise, just ensure the `bank_system.py` file (or whatever you name it) is in a folder on your computer.

```bash
git clone [https://github.com/Sohail-Ansari-afk/Bank-Management-System.git](https://github.com/Sohail-Ansari-afk/Bank-Management-System.git)
cd Bank-Management-System
