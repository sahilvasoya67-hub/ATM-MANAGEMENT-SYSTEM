
#include <iostream>
#include <vector>
#include <string>
using namespace std;

// Global variables
float balance = 1000.0;
vector<string> history;
int PIN = 1234;

// Function to add history entry
void addHistory(string entry) {
    history.push_back(entry);
}

// Function to show transaction history
void showHistory() {
    if (history.empty()) {
        cout << "\nNo transactions yet.\n";
        return;
    }

    cout << "\n----- Transaction History -----\n";
    for (int i = 0; i < history.size(); i++) {
        cout << i + 1 << ". " << history[i] << endl;
    }
    cout << "--------------------------------\n";
}

// Main program
int main() {
    int enteredPin, attempts = 0, choice;
    float amount;

    // PIN Verification with 3 attempts
    while (attempts < 3) {
        cout << "Enter your 4-digit PIN: ";
        cin >> enteredPin;

        if (enteredPin == PIN) {
            cout << "Access Granted!\n";
            break;
        } else {
            attempts++;
            cout << "Incorrect PIN! Attempts left: " << 3 - attempts << endl;
        }
    }

    if (attempts == 3) {
        cout << "\nYour account is locked due to too many wrong attempts!\n";
        return 0;
    }

    // Main ATM menu
    while (true) {
        cout << "\n----- MINI ATM -----\n";
        cout << "1. Check Balance\n";
        cout << "2. Deposit Money\n";
        cout << "3. Withdraw Money\n";
        cout << "4. Transaction History\n";
        cout << "5. Exit\n";
        cout << "Choose an option: ";
        cin >> choice;

        switch (choice) {
        case 1:
            cout << "\nYour Balance: " << balance << " Rs\n";
            addHistory("Checked Balance");
            break;

        case 2:
            cout << "\nEnter amount to deposit: ";
            cin >> amount;

            if (amount <= 0) {
                cout << "Invalid amount!\n";
            } else {
                balance += amount;

                addHistory("Deposited: " + to_string(amount) + " Rs");

                cout << "Successfully deposited " << amount << " Rs\n";
            }
            break;

        case 3:
            cout << "\nEnter amount to withdraw: ";
            cin >> amount;

            if (amount <= 0) {
                cout << "Invalid amount!\n";
            }
            else if (amount > balance) {
                cout << "Insufficient balance!\n";
            } 
            else {
                balance -= amount;

                addHistory("Withdrawn: " + to_string(amount) + " Rs");

                cout << "Successfully withdrawn " << amount << " Rs\n";
            }
            break;

        case 4:
            showHistory();
            break;

        case 5:
            cout << "\nThank you for using the ATM!\n";
            return 0;

        default:
            cout << "Invalid choice! Try again.\n";
        }
    }

    return 0;
}
