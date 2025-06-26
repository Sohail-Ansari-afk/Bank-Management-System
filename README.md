# Bank Management System

A simple command-line interface (CLI) bank management system built with Python, using SQLAlchemy for database management and bcrypt for secure password hashing. This system allows users to register, log in, create accounts, deposit, withdraw, and transfer funds. It also includes an admin interface for managing users and viewing all system data.

## Features

  * **User Authentication:** Secure user registration and login with bcrypt for password hashing.
  * **User Roles:** Differentiates between 'user' and 'admin' roles.
  * **Account Management:**
      * Create new bank accounts (savings, checking, etc.).
      * View user-specific accounts.
      * Generate unique 10-digit account numbers.
  * **Transaction Management:**
      * Deposit funds into an account.
      * Withdraw funds from an account.
      * Transfer funds between accounts.
      * View detailed transaction history for any account.
  * **Admin Dashboard:**
      * View all registered users.
      * Toggle user active/inactive status.
      * View all bank accounts in the system.
      * View all transactions across the system.
      * Search users by username.
  * **Database Integration:** Uses SQLAlchemy to interact with a SQLite database by default (can be configured for others).
  * **Cross-platform:** Works on Windows, macOS, and Linux.

## Technologies Used

  * **Python 3.x**
  * **SQLAlchemy:** ORM (Object Relational Mapper) for database interactions.
  * **Bcrypt:** For secure password hashing.
  * **`os` and `sys` modules:** For system commands and exit.
  * **`random` and `string` modules:** For generating account numbers.
  * **`datetime` module:** For timestamps.

## Getting Started

Follow these instructions to set up and run the Bank Management System on your local machine.

### Prerequisites

  * Python 3.7 or newer installed on your system. You can download it from [python.org](https://www.python.org/downloads/).

### Installation

1.  **Clone the repository (or download the code):**
    If you have Git installed (recommended):

    ```bash
    git clone https://github.com/Sohail-Ansari-afk/Bank-Management-System.git
    cd Bank-Management-System
    ```

    If you don't have Git, download the code as a ZIP file and extract it to your desired location. Then navigate into the extracted folder using your terminal/command prompt.

2.  **Create a Virtual Environment (Recommended):**
    It's good practice to create a virtual environment to manage project dependencies.

    ```bash
    python -m venv venv
    ```

3.  **Activate the Virtual Environment:**

      * **On Windows:**
        ```bash
        .\venv\Scripts\activate
        ```
      * **On macOS/Linux:**
        ```bash
        source venv/bin/activate
        ```

    You should see `(venv)` at the beginning of your terminal prompt, indicating the virtual environment is active.

4.  **Install Dependencies:**
    You'll need `SQLAlchemy` and `bcrypt`.

    ```bash
    pip install SQLAlchemy bcrypt
    ```

### Running the Application

1.  **Navigate to the project directory** (if you're not already there):

    ```bash
    cd Bank-Management-System
    ```

    (Replace `Bank-Management-System` with the actual folder name if different)

2.  **Ensure your virtual environment is activated** (as per step 3 in Installation).

3.  **Run the main script:**

    ```bash
    python your_script_name.py
    ```

    *(Assuming your Python file is named `your_script_name.py`. If you've copied the code into a file named, say, `bank_app.py`, then you'd run `python bank_app.py`)*

    When you run it for the first time, it will automatically create a `bank.db` SQLite database file in the same directory.

### Usage

The application is a command-line interface. Follow the on-screen prompts.

1.  **Main Menu:**

      * `1. Register New Account`: Create a new user account.
      * `2. Login`: Log in as an existing user or admin.
      * `3. Exit`: Close the application.

2.  **User Menu (after logging in as a 'user'):**

      * `1. View My Accounts`: See all bank accounts associated with your user ID.
      * `2. Create New Bank Account`: Add a new account (e.g., 'savings', 'checking').
      * `3. Deposit Funds`: Add money to an account.
      * `4. Withdraw Funds`: Remove money from an account.
      * `5. Transfer Funds`: Move money between accounts.
      * `6. View Account Transaction History`: See a list of transactions for a specific account.
      * `7. Logout`: Return to the Main Menu.

3.  **Admin Menu (after logging in as an 'admin'):**

      * `1. View All System Users`: See all registered users.
      * `2. Toggle User Active Status`: Activate or deactivate a user's login ability.
      * `3. View All Bank Accounts`: See all accounts in the system.
      * `4. View All System Transactions`: See all transactions across all accounts.
      * `5. Search User by Username`: Find users by partial or full username.
      * `6. Logout`: Return to the Main Menu.

#### Creating an Admin User

To access the admin functionalities, you'll need to manually create an admin user. You can modify the `register_user` call or directly insert an admin user into the database if needed, but for simplicity, you can:

1.  Run the application.
2.  Register a new user (e.g., username `admin`, password `adminpass`).
3.  **Temporarily modify your script** (before running `run_app()` or just after `init_db()`) to manually change that user's role to 'admin' in the database.
    ```python
    # After init_db(), auth_manager = AuthManager(), etc.
    # Add this temporarily to make an admin user
    session = Session()
    try:
        admin_user = session.query(User).filter_by(username='admin').first()
        if admin_user and admin_user.role != 'admin':
            admin_user.role = 'admin'
            session.commit()
            print("User 'admin' role updated to admin.")
    except Exception as e:
        session.rollback()
        print(f"Error making user admin: {e}")
    finally:
        session.close()
    ```
    Remember to remove or comment out this temporary code after running it once and confirming the admin user's role.

Alternatively, you could add a dedicated `register_admin_user` function for initial setup if this were a production application.

-----
