Bank Account Management System (Java)

This project is a basic console-based banking application built in Java.
It demonstrates key OOP concepts such as encapsulation, methods, and data validation.

📂 Files

BankAccount.java — Defines the BankAccount class with deposit, withdraw, and balance display methods.

Bank.java — Contains the main() method to interact with the user via console input.

💻 Code
🧩 BankAccount.java
public class BankAccount {
    private int balance; // private variable ensures encapsulation

    // Returns current balance
    public int showBalance() {
        return balance;
    }

    // Method to deposit amount
    public void deposite(int amount) {
        if (amount > 0) {
            balance += amount;
        } else {
            System.out.println("Please enter a positive amount");
        }
    }

    // Method to withdraw amount
    public void withDraw(int amount) {
        if (amount >= 0) {
            if (balance <= 0) {
                System.out.println("Insufficient funds");
            } else {
                balance -= amount;
            }
        } else {
            System.out.println("Please enter a positive amount");
        }
    }
}

🧭 Bank.java
import java.util.Scanner;

public class Bank {
    public static void main(String[] args) {
        BankAccount account = new BankAccount();
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter 1 for Deposit \n2 for Withdraw");
        int option = sc.nextInt();

        if (option == 1) {
            System.out.print("Enter amount to deposit: ");
            int amount = sc.nextInt();
            account.deposite(amount);
            System.out.println("Your account balance: " + account.showBalance());
        } 
        else if (option == 2) {
            System.out.print("Enter amount to withdraw: ");
            int amount = sc.nextInt();
            account.withDraw(amount);
            System.out.println("Your account balance: " + account.showBalance());
        } 
        else {
            System.out.println("Enter a valid option!");
        }

        sc.close();
    }
}

🧠 Concept Used

Encapsulation → The balance variable is private and accessed only via methods.

Validation → Ensures user cannot deposit or withdraw invalid amounts.

Conditional Statements → Used for option handling and input validation.

User Input → Uses Scanner for interactive input.

✅ Sample Output
Case 1: Deposit
Enter 1 for Deposit 
2 for Withdraw
1
Enter amount to deposit: 5000
Your account balance: 5000

Case 2: Withdraw
Enter 1 for Deposit 
2 for Withdraw
2
Enter amount to withdraw: 2000
Your account balance: 3000

Case 3: Invalid Option
Enter 1 for Deposit 
2 for Withdraw
3
Enter a valid option!

🚀 How to Run

Save both files (BankAccount.java and Bank.java) in the same folder.

Open a terminal in that folder.

Compile the files:

javac BankAccount.java Bank.java


Run the program:

java Bank

📘 Example Scenarios
Action	Input	Result
Deposit	1 → 1000	Adds 1000 to balance
Withdraw	2 → 500	Deducts 500 if sufficient funds
Invalid	3	Prompts “Enter a valid option”
🧩 Key Learning

How to use multiple classes in a single Java project

Applying encapsulation to protect data

Implementing conditional logic and user input handling
