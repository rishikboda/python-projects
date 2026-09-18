# 🏦 Python ATM Banking System

A simple **ATM Banking System** built using Python.
This beginner-friendly project allows a user to check their balance, deposit money, withdraw money, and exit the banking system using a PIN-based authentication system.

## 📌 Features

* 🔐 PIN-based authentication
* 💰 Check available account balance
* ➕ Deposit money
* ➖ Withdraw money
* 🚫 Prevent withdrawal when the balance is insufficient
* 👤 Display account holder name
* 🏦 Display account number
* 🔄 Continuous menu using a `while` loop
* ❌ Exit the banking system

## 🛠️ Technologies Used

* **Python 3**
* `while` loop
* `if-elif-else` statements
* Variables
* User input using `input()`
* Formatted strings (f-strings)
* Arithmetic operators

## 📋 Banking Menu

```text
1 : To check the balance
2 : To deposit
3 : To withdraw
4 : To exit
```

## 🔐 Default Account Details

For demonstration purposes, the program contains sample account information:

```text
Account Holder: rishik
PIN: 1234
Initial Balance: ₹10,000
```

> ⚠️ This is an educational project. The PIN and account information are stored directly in the Python code and should **not** be used for a real banking application.

## ⚙️ How the Program Works

### 1. Check Balance

The user selects option `1` and enters:

* Account number
* PIN

If the PIN is correct, the program displays the account balance and account holder's name.

### 2. Deposit Money

The user selects option `2`.

After successful PIN verification, the user enters the amount to deposit.

The balance is updated using:

```python
balance += amount
```

### 3. Withdraw Money

The user selects option `3`.

After successful PIN verification, the user enters the withdrawal amount.

The program checks whether enough money is available:

```python
if amount <= balance:
    balance -= amount
```

If the requested amount is greater than the available balance, the program displays:

```text
insufficient balance
```

### 4. Exit

The user selects option `4`.

The program displays a thank-you message and terminates the loop using:

```python
break
```

## ▶️ How to Run

### Step 1: Install Python

Make sure Python 3 is installed on your computer.

You can check it using:

```bash
python --version
```

### Step 2: Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### Step 3: Open the Project Folder

```bash
cd YOUR_PROJECT_FOLDER
```

### Step 4: Run the Program

```bash
python atm.py
```

## 💻 Example Output

```text
"1" : to check the balance
"2" : to deposit
"3" : to withdrawl
"4" : to exit

enter the choice: 1
enter the account number: 123456
enter your pin number: 1234

your available balance = 10000
account holder name = rishik
```

## 📚 Python Concepts Practiced

This project helped practice:

* Variables
* Data types
* `while` loops
* Conditional statements
* `break`
* User input
* Type conversion using `int()`
* Arithmetic operators
* Comparison operators
* f-strings
* Basic authentication logic

## 🚀 Future Improvements

This project can be improved by adding:

* Multiple bank accounts
* Multiple users
* Account number verification
* PIN change functionality
* Transaction history
* Transfer money between accounts
* Input validation
* File/database storage
* A graphical user interface (GUI)
* Better security for passwords/PINs

## 🎯 Learning Objective

The main objective of this project is to understand how Python programming concepts can be combined to create a simple **real-world banking application**.

---

### 👨‍💻 Author

**Rishik**

B.Tech Student

Python Beginner Project
