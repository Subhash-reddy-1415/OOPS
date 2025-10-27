Student Constructor Example in Java

This Java program demonstrates the concept of constructors, including both default and parameterized constructors, using a simple Student class example.

📂 Files

StudentN.java → Defines the StudentN class with constructors.

StudentApp.java → Contains the main() method that creates StudentN objects and displays their details.

💻 Code
🧩 StudentN.java
public class StudentN {
    int id;
    String name;

    // Parameterized constructor
    public StudentN(int id, String name) {
        this.id = id;
        this.name = name;
    }

    // Default constructor
    public StudentN() {
    }
}

🧭 StudentApp.java
public class StudentApp {
    public static void main(String[] args) {
        
        // Using parameterized constructor
        StudentN student2 = new StudentN(10, "Rithvik");
        System.out.println(student2.id + " " + student2.name);

        // Using default constructor and setting values later
        StudentN student = new StudentN();
        student.id = 12;
        student.name = "Sathvik";
        System.out.println(student.id + " " + student.name);
    }
}

✅ Sample Output
10 Rithvik
12 Sathvik

⚙️ Explanation
🔹 Default Constructor

A constructor with no parameters.

It’s used when we want to create an object first and then assign values later.

StudentN student = new StudentN();
student.id = 12;
student.name = "Sathvik";

🔹 Parameterized Constructor

A constructor that accepts parameters.

Used to initialize object properties directly during object creation.

StudentN student2 = new StudentN(10, "Rithvik");

🧠 Key Concepts Used
Concept	Description
Constructor	Special method used to initialize objects
this keyword	Refers to the current object, used to differentiate between instance and parameter variables
Object creation	new keyword used to create objects
Encapsulation (basic)	Data members (id, name) are grouped together inside the class
🚀 How to Run

Save both files (StudentN.java and StudentApp.java) in the same directory.

Open the terminal and compile both files:

javac StudentN.java StudentApp.java


Run the main class:

java StudentApp

🧩 Key Learning Outcomes

✅ Understand how constructors work in Java.
✅ Differentiate between default and parameterized constructors.
✅ Learn how to initialize and access object data members.
