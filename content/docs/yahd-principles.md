+++
title = 'OOP Principles'
date = 2023-10-17T12:06:05+01:00
draft = false
+++

### 1. Encapsulation

#### Meaning:
It's about bundling the data (attributes) and the methods (functions) that operate on the data into a single unit called an object. Moreover, restricting direct access to some of an object's components, which is a means to prevent unintended interference and misuse of data.

#### Java Example:
Using private modifiers for class attributes and providing public getters and setters to access and modify them.

```java
    public class Person {
        private String name;

        public String getName() {
            return name;
        }

        public void setName(String name) {
            this.name = name;
        }
    }
```

### 2. Abstraction

#### Meaning:
It's about hiding the complex implementation details and showing only the necessary features of an object. This simplifies external interaction with the object and reduces the impact of change.

#### Example:
A car, in essence, can be started with a key without understanding the inner workings of its engine.

### 3. Inheritance

#### Meaning:
A mechanism where a new class inherits properties and behaviors (methods) from an existing class. It promotes code reuse and establishes a natural hierarchy between classes.

#### Java Example:
Creating a Vehicle class with general attributes and methods, and then deriving more specific vehicle types like Car or Motorcycle from it.

```java
    public class Vehicle {
        public void move() {/*...*/}
    }

    public class Car extends Vehicle {
        public void honk() {/*...*/}
    }
```

### 4. Polymorphism

#### Meaning:
It allows objects of different classes to be treated as objects of a common super class. More precisely, it's the ability of different classes to be treated as instances of the same class through inheritance.

#### Java Example:
Having multiple shapes like Circle and Rectangle that can all be displayed through a common method, perhaps defined in an interface like Shape.

```java
    public interface Shape {
        void draw();
    }

    public class Circle implements Shape {
        @Override
        public void draw() {
            System.out.println("Drawing a circle");
        }
    }

    public class Rectangle implements Shape {
        @Override
        public void draw() {
            System.out.println("Drawing a rectangle");
        }
    }
```
