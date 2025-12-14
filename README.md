# LabReport01 – Inheritance in Java

This repository contains the source code and documentation for **LabReport01**, which demonstrates the concept of **inheritance and method overriding in Java** using an employee hierarchy.

---

##  Problem Description

The objective of this lab is to model an employee hierarchy using Java inheritance:

- Create a base class `Employee` with common attributes.
- Derive a subclass `Manager` from `Employee`.
- Override methods to demonstrate runtime polymorphism.
- Create objects of both classes and display their information.

---

##  Concepts Used

- Object-Oriented Programming (OOP)
- Inheritance
- Method Overriding
- Polymorphism
- `super` keyword

---

## Class Structure

### 1. Employee (Base Class)
**Fields:**
- `name` (String)
- `id` (int)
- `basicSalary` (double)

**Method:**
- `displayInfo()` – Displays employee details

---

### 2. Manager (Derived Class)
**Additional Field:**
- `department` (String)

**Overridden Method:**
- `displayInfo()` – Displays employee details along with department

---## UML Class Diagram

    +----------------+
    |   Employee     |
    +----------------+
    | - name         |
    | - id           |
    | - basicSalary  |
    +----------------+
    | + displayInfo()|
    +----------------+
           ^
           |
    +----------------+
    |   Manager      |
    +----------------+
    | - department   |
    +----------------+
    | + displayInfo()|
    +----------------+

---

## Source Code

### Employee.java
```java
class Employee {
    protected String name;
    protected int id;
    protected double basicSalary;

    public Employee(String name, int id, double basicSalary) {
        this.name = name;
        this.id = id;
        this.basicSalary = basicSalary;
    }

    public void displayInfo() {
        System.out.println("Employee Details:");
        System.out.println("Name: " + name);
        System.out.println("ID: " + id);
        System.out.println("Basic Salary: " + basicSalary);
    }
}
class Manager extends Employee {
    private String department;

    public Manager(String name, int id, double basicSalary, String department) {
        super(name, id, basicSalary);
        this.department = department;
    }

    @Override
    public void displayInfo() {
        super.displayInfo();
        System.out.println("Department: " + department);
    }
}
public class Main {
    public static void main(String[] args) {
        Employee emp = new Employee("Rofiq", 101, 35000);
        Manager mgr = new Manager("Karim", 201, 55000, "HR");

        emp.displayInfo();
        System.out.println();
        mgr.displayInfo();
    }
}
 How to Run the Program
Clone the repository:
git clone <your-repository-link>
Compile the program
javac Main.java
Run the program
java Main
Sample Output
Employee Details:
Name: Karim
ID: 101
Basic Salary: 35000.0

Employee Details:
Name: Bob
ID: 201
Basic Salary: 55000.0
Department: HR
