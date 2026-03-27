# ATM_MANAGEMENT_SYSTEM
C++ ATM MANAGEMENT SYSTEM USING OOPS
# 🏦 ATM Management System (C++)

## 📌 Introduction

The ATM Management System is a simple console-based application developed using **C++** and **Object-Oriented Programming (OOP)** concepts. This system simulates basic ATM operations such as checking balance, depositing money, withdrawing cash, and viewing account details.

It is designed for learning purposes to understand how real-world banking systems work in a simplified way.

---

## 🎯 Objectives of the Project

* To implement real-world ATM functionalities using C++
* To apply OOP concepts like **classes, encapsulation, and abstraction**
* To manage user account data securely
* To create a user-friendly menu-driven system

---

## 🧠 Methodology / System Design

The system is designed using:

* **Class:** `ATM`
* **Private Data Members:**

  * Account Holder Name
  * Account Number
  * Balance
* **Public Member Functions:**

  * Check Balance
  * Deposit Money
  * Withdraw Money
  * Display Account Details

### 🔄 Flow of System:

1. User enters ATM system
2. Menu is displayed
3. User selects an operation
4. System processes request
5. Output is displayed

---

## 💻 Implementation / Source Code

```cpp
#include <iostream>
using namespace std;

class ATM {
private:
    string name;
    int accountNumber;
    double balance;

public:
    void createAccount() {
        cout << "Enter Account Holder Name: ";
        cin >> name;
        cout << "Enter Account Number: ";
        cin >> accountNumber;
        cout << "Enter Initial Balance: ";
        cin >> balance;
    }

    void checkBalance() {
        cout << "Current Balance: " << balance << endl;
    }

    void deposit() {
        double amount;
        cout << "Enter amount to deposit: ";
        cin >> amount;
        balance += amount;
        cout << "Amount Deposited Successfully!\n";
    }

    void withdraw() {
        double amount;
        cout << "Enter amount to withdraw: ";
        cin >> amount;
        if (amount > balance) {
            cout << "Insufficient Balance!\n";
        } else {
            balance -= amount;
            cout << "Withdrawal Successful!\n";
        }
    }

    void displayDetails() {
        cout << "\nAccount Holder: " << name;
        cout << "\nAccount Number: " << accountNumber;
        cout << "\nBalance: " << balance << endl;
    }
};

int main() {
    ATM user;
    int choice;

    user.createAccount();

    do {
        cout << "\n\n===== ATM MENU =====\n";
        cout << "1. Check Balance\n";
        cout << "2. Deposit Money\n";
        cout << "3. Withdraw Money\n";
        cout << "4. Display Account Details\n";
        cout << "5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1: user.checkBalance(); break;
            case 2: user.deposit(); break;
            case 3: user.withdraw(); break;
            case 4: user.displayDetails(); break;
            case 5: cout << "Thank you for using ATM!\n"; break;
            default: cout << "Invalid choice!\n";
        }
    } while (choice != 5);

    return 0;
}
```

---

## ⚙️ Features

* Menu-driven interface
* Secure handling of account balance
* Deposit and withdrawal functionality
* Prevents overdrawing
* Simple and easy to use

---

## 📊 Output (Sample)

```
===== ATM MENU =====
1. Check Balance
2. Deposit Money
3. Withdraw Money
4. Display Account Details
5. Exit
```

---

## 📌 Conclusion

The ATM Management System project demonstrates how basic banking operations can be implemented using C++ and OOP concepts. It improves understanding of class design, data handling, and user interaction.

## 👨‍💻 Author

Sahil Vasoya
B.Tech CSE (1st Year)
JG University

---
