+++
title = 'SOLID Principles'
date = 2023-10-17T12:06:05+01:00
draft = false
+++

### 1. Single Responsibility Principle (SRP)

#### Meaning:
A class should have only one reason to change, meaning it should have only one job or responsibility.

#### Java Example:
Instead of a single class handling both data storage and data representation, you split these tasks into separate classes.

```java
    // Combining responsibilities (not ideal)
    public class User {
        public void saveUserToDatabase() {/*...*/}
        public void displayUserDetails() {/*...*/}
    }

    // Split responsibilities (preferred)
    public class UserDatabase {
        public void saveUser(User user) {/*...*/}
    }

    public class UserDetailsRenderer {
        public void displayUserDetails(User user) {/*...*/}
    }
```

### 2. Open/Closed Principle (OCP)

#### Meaning:
Classes should be open for extension but closed for modification. You should be able to add new functionality without changing existing code.

#### Java Example:
By using interfaces or abstract classes, new functionality can be added without changing existing code.

```java
    public interface Shape {
        double area();
    }

    public class Circle implements Shape {
        private double radius;
        public Circle(double radius) { this.radius = radius; }
        @Override
        public double area() { return Math.PI * radius * radius; }
    }

    public class Rectangle implements Shape {
        private double width, height;
        public Rectangle(double width, double height) { this.width = width; this.height = height; }
        @Override
        public double area() { return width * height; }
    }
```

### 3. Liskov Substitution Principle (LSP)

#### Meaning:
Objects of a superclass should be able to be replaced with objects of a subclass without affecting the correctness of the program.

#### Java Example:
Ensuring that overridden methods in subclasses maintain the "contract" set by the superclass.

```java
    public class Bird {
        public void fly() {/*...*/}
    }

    public class Ostrich extends Bird {
        // An ostrich cannot fly, so overriding the fly method or throwing an exception would violate LSP.
    }
```

### 4. Interface Segregation Principle (ISP)

#### Meaning:
A class should not be forced to implement interfaces it doesn't use. Instead of one large interface, several smaller, specific interfaces are better.

#### Java Example:
The example does all the talking here!

```java
    // Instead of one large interface
    public interface Worker {
        void work();
        void eat();
    }

    // Use smaller, specific interfaces
    public interface Workable {
        void work();
    }

    public interface Eatable {
        void eat();
    }
```

### 5. Dependency Inversion Principle (DIP)

#### Meaning:
High-level modules (classes) should not depend on low-level modules. Both should depend on abstractions (interfaces or abstract classes).

#### Java Example:
Instead of a switch class directly depending on a light bulb, they both depend on an interface.

```java
    public interface Switchable {
        void turnOn();
        void turnOff();
    }

    public class LightBulb implements Switchable {
        @Override
        public void turnOn() {/*...*/}
        @Override
        public void turnOff() {/*...*/}
    }

    public class Switch {
        private Switchable device;
        public Switch(Switchable device) { this.device = device; }
        // use device here
    }
```