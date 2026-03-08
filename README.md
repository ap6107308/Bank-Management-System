# Bank Management System

A Python-based **Banking Management System** that utilizes **MySQL** for secure data persistence. This application allows users to register, manage bank accounts, perform financial transactions, and track account history through a command-line interface.

---

## 🚀 Key Features

* **User Authentication:** Secure registration and login system for bank administrators or users.
* **Account Management:** Create new customer accounts with details like name, phone number, address, and initial credit.
* **Financial Transactions:** Support for both withdrawing and adding (depositing) funds to existing accounts.
* **Real-time Updates:** Automatically calculates and updates account balances in the database after every transaction.
* **Data Retrieval:** View specific customer profiles or a complete history of all transactions associated with an account.
* **Account Deletion:** Capability to permanently remove customer records from the system.

---

## 🛠️ Prerequisites

* **Python 3.x**
* **MySQL Server**
* **Required Library:**
```bash
pip install mysql-connector-python

```



---

## 📂 Project Structure

| File | Description |
| --- | --- |
| `main bank.py` | The entry point. Handles the initial "Welcome" screen, user registration, and login. |
| `menu.py` | The core application logic containing the main banking menu and transaction functions. |
| `user_table.py` | Database script to create the `user_table` for login credentials. |
| `table.py` | Database script to create the `customer_details` table. |
| `transaction_table.py` | Database script to create the `transactions` table for logging all activity. |

---

## ⚙️ Setup & Installation

1. **Configure MySQL:** Ensure your MySQL server is running. The scripts currently use the following default credentials (update these in all `.py` files to match your local setup):
* **Host:** `localhost`
* **User:** `root`
* **Password:** `manager`
* **Database:** `bank`


2. **Initialize Database Tables:**
Run the following scripts in order to set up the database schema:
```bash
python user_table.py
python table.py
python transaction_table.py

```


3. **Run the Application:**
Start the system by running the main file:
```bash
python "main bank.py"

```



---

## 📊 Database Schema

* **user_table:** Stores `username` (Primary Key) and `passwrd`.
* **customer_details:** Stores `acct_no` (Primary Key), `acct_name`, `phone_no`, `address`, and `cr_amt` (balance).
* **transactions:** Logs `acct_no`, `date`, `withdrawal_amt`, and `amount_added` for every movement of funds.

---

## ⚠️ Usage Notes

* **Password Format:** The system currently expects a **4-digit integer** for passwords during registration and login.
* **Registration Flow:** After a successful registration, the system automatically redirects to the banking menu.
* **Input Validation:** Ensure account numbers are created before attempting transactions, otherwise, the system will report an "Account Number Invalid" error.
