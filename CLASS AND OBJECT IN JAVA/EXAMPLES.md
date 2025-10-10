# 🧩 Class and Object in Java

## 📘 Concept Overview

In **Java**, a **Class** is a blueprint or template that defines the **attributes (data members)** and **behaviors (methods)** of objects.  
An **Object** is an instance of a class — it represents a real-world entity that has a **state** and **behavior**.

---

## 🔹 Class

A **class** defines the structure and behavior of objects.  
It contains:
- **Fields (variables):** store data or state.
- **Methods (functions):** define actions or behavior.

**Syntax:**
```java
class ClassName {
    // Data members
    // Member methods
}
🔹 Object
An object is created from a class using the new keyword.
Each object has its own copy of the class's instance variables.

Syntax:

java
Copy code
ClassName objectName = new ClassName();
🧠 Example Program
java
Copy code
// File: Student.java
```

class Student {
    // Data members
    String name;
    int age;

    // Method
    void display() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }

    public static void main(String[] args) {
        // Object creation
        Student s1 = new Student();

        // Assign values
        s1.name = "Alice";
        s1.age = 20;

        // Method call
        s1.display();
    }
}

```
Output:

makefile
Copy code
Name: Alice
Age: 20
⚙️ How It Works
The Student class defines the structure (name, age, display method).

Student s1 = new Student(); creates an object of Student.

The object s1 accesses class members using the dot (.) operator.

s1.display(); executes the method for that particular object.

🧩 Key Points
A class is a logical structure — it doesn’t occupy memory until an object is created.

An object represents a specific instance with actual data.

The dot operator (.) is used to access members of a class through an object.

Multiple objects can be created from the same class.

📂 File Structure
Copy code
OOPS/
│
├── ClassAndObject/
│   ├── Student.java
│   └── README.md
🧑‍💻 Author
Your Name
📧 [your.email@example.com]
🌐 https://github.com/yourusername

⭐ Notes
This example demonstrates the fundamental concept of Class and Object —
the foundation of Object-Oriented Programming (OOP) in Java.
