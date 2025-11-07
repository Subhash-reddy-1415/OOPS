Simple Bank Account Management System (Java)
📘 Overview

This Java project simulates a basic bank account system using OOP principles.
It allows users to create a bank account and perform common operations such as:

Depositing money

Withdrawing money

Checking balance

Changing PIN

The program demonstrates Encapsulation by keeping sensitive data (like PIN and balance) private and allowing access only through controlled public methods.

📂 Files

SBankAccount.java — Contains the SBankAccount class with all account operations.

MainSBank.java — Contains the main() method for user interaction (menu-based console system).

💻 Code
🧩 SBankAccount.java
public class SBankAccount {
    private String accountNumber;
    private String accountHolderName;
    private double accountBalance;
    private int pin;
    
    public SBankAccount(String accountNumber, String accountHolderName, double accountBalance, int pin) {
        this.accountNumber = accountNumber;
        this.accountHolderName = accountHolderName;
        this.accountBalance = accountBalance;
        this.pin = pin;
    }
    
    public String getNumber() {
        return accountNumber;
    }
    public String getName() {
        return accountHolderName;
    }
    
    public void deposite(int pinCode, double amount) {
        if(pinCode == pin) {
            if(amount > 0) {
                System.out.println("Deposit Successful!");
                accountBalance += amount;
                System.out.println("New balance = " + accountBalance);
            } else {
                System.out.println("Please enter an amount greater than 0.");
            }
        } else {
            System.out.println("Incorrect PIN! Deposit failed.");
        }
    }
    
    public void withdraw(int pinCode, double amount) {
        if(pinCode == pin) {
            if(amount <= accountBalance) {
                System.out.println("Withdrawal Successful!");
                accountBalance -= amount;
                System.out.println("New balance = " + accountBalance);
            } else {
                System.out.println("Insufficient Balance!");
            }
        } else {
            System.out.println("Incorrect PIN! Withdraw failed.");
        }
    }
    
    public void checkBalance(int pinCode) {
        if(pinCode == pin) {
            System.out.println("Your current balance is = " + accountBalance);
        } else {
            System.out.println("Incorrect PIN!");
        }
    }
    
    public void changePin(int oldPin, int newPin) {
        if(oldPin == pin) {
            this.pin = newPin;
            System.out.println("PIN changed successfully!");
        } else {
            System.out.println("Incorrect old PIN!");
        }
    }
}

🧩 MainSBank.java
import java.util.Scanner;

public class MainSBank {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        System.out.println("ENTER ACCOUNT NUMBER = ");
        String accountNumber = sc.nextLine();
        
        System.out.println("ENTER ACCOUNT HOLDER NAME = ");
        String accountHolderName = sc.nextLine();
        
        System.out.println("ENTER INITIAL BALANCE = ");
        double accountBalance = sc.nextDouble();
        
        System.out.println("ENTER YOUR PIN = ");
        int pin = sc.nextInt();
        
        SBankAccount account = new SBankAccount(accountNumber, accountHolderName, accountBalance, pin);
        
        System.out.println("\n\t** PLEASE SELECT ONE OPTION **");
        System.out.println("1. MONEY DEPOSIT");
        System.out.println("2. MONEY WITHDRAW");
        System.out.println("3. CHECK BALANCE");
        System.out.println("4. CHANGE PIN");
        
        int option = sc.nextInt();
        
        switch(option) {
            case 1:
                System.out.println("Enter your PIN = ");
                int pinCode = sc.nextInt();
                System.out.println("Enter deposit amount = ");
                double amount = sc.nextDouble();            
                account.deposite(pinCode, amount);
                break;
                
            case 2:
                System.out.println("Enter your PIN = ");
                int pinN1 = sc.nextInt();
                System.out.println("Enter withdrawal amount = ");
                double amount1 = sc.nextDouble();
                account.withdraw(pinN1, amount1);
                break;
                
            case 3:
                System.out.println("Enter your PIN to check balance = ");
                int pin1 = sc.nextInt();
                account.checkBalance(pin1);
                break;
                
            case 4:
                System.out.println("Enter old PIN = ");
                int oldPin = sc.nextInt();
                System.out.println("Enter new PIN = ");
                int newPin = sc.nextInt();
                account.changePin(oldPin, newPin);
                break;
                
            default:
                System.out.println("INVALID OPTION!");
        }
    }
}

🧠 Explanation
Feature	Description
Encapsulation	All sensitive fields are private (accountBalance, pin) and accessed only via public methods.
Constructor	Initializes a new account with details like number, name, balance, and PIN.
Deposit Method	Adds money after verifying PIN.
Withdraw Method	Deducts money if balance is sufficient and PIN is correct.
Balance Check	Displays account balance securely.
PIN Change	Updates PIN after verifying the old one.
Switch-Case Menu	Handles user selection for various operations.
🧩 Example Run

Input:

ENTER ACCOUNT NUMBER = 123456
ENTER ACCOUNT HOLDER NAME = Subhash
ENTER INITIAL BALANCE = 5000
ENTER YOUR PIN = 1234
** PLEASE SELECT ONE OPTION **
1. MONEY DEPOSIT
2. MONEY WITHDRAW
3. CHECK BALANCE
4. CHANGE PIN


Option:

1
Enter your PIN = 1234
Enter deposit amount = 1500


Output:

Deposit Successful!
New balance = 6500.0

🧱 Key Concepts Used
Concept	Description
Encapsulation	Private fields + public getter/setter methods.
Class Interaction	MainSBank creates and uses SBankAccount objects.
Control Statements	switch-case, if-else for decision making.
Scanner	Takes user input from console.
🚀 How to Run

Save both files in the same folder:

SBankAccount.java
MainSBank.java


Compile both files:

javac SBankAccount.java MainSBank.java


Run the program:

java MainSBank

🏁 Sample Output
ENTER ACCOUNT NUMBER = 12345
ENTER ACCOUNT HOLDER NAME = Reddy
ENTER INITIAL BALANCE = 10000
ENTER YOUR PIN = 1111
** PLEASE SELECT ONE OPTION **
1. MONEY DEPOSIT
2. MONEY WITHDRAW
3. CHECK BALANCE
4. CHANGE PIN


Output (example for withdrawal):

Enter your pin = 1111
Enter withdraw amount = 2000
Withdrawal Successful!
New balance = 8000.0
