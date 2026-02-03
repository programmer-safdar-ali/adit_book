# Chapter 6: Object-Oriented Programming (OOP)

## Introduction

Object-Oriented Programming (OOP) is a programming paradigm that organizes code around objects and classes rather than functions and logic. As an Assistant Director IT, understanding OOP concepts is crucial for evaluating software solutions, understanding system architecture, and making informed decisions about development methodologies. This chapter covers the core OOP concepts, design patterns, and principles.

## Core OOP Concepts

### Encapsulation: Data Hiding, Getters/Setters

#### Definition
- **Encapsulation**: Bundling data and methods that operate on that data within a single unit (class)
- **Purpose**: Hide internal implementation details and expose only necessary functionality
- **Benefits**: Increased security, maintainability, and flexibility

#### Data Hiding
- **Concept**: Restrict access to internal components of an object
- **Implementation**: Access modifiers (public, private, protected)
- **Private Members**: Accessible only within the class
- **Protected Members**: Accessible within the class and derived classes
- **Public Members**: Accessible from anywhere

#### Getters and Setters
- **Getters**: Methods to retrieve private data
- **Setters**: Methods to modify private data
- **Validation**: Setters can include validation logic
- **Example**:
```java
public class BankAccount {
    private double balance;
    
    public double getBalance() {
        return balance;
    }
    
    public void setBalance(double amount) {
        if (amount >= 0) {
            this.balance = amount;
        } else {
            throw new IllegalArgumentException("Balance cannot be negative");
        }
    }
}
```

### Inheritance: Single, Multiple, Multilevel, Hierarchical

#### Definition
- **Inheritance**: Mechanism where one class acquires properties and methods of another class
- **Parent/Superclass**: Class whose properties are inherited
- **Child/Subclass**: Class that inherits properties
- **Benefits**: Code reusability, method overriding, polymorphism

#### Types of Inheritance

##### Single Inheritance
- **Concept**: One class inherits from one parent class
- **Example**: Dog extends Animal
- **Languages**: Java, C#, Python (single inheritance from one class)

##### Multiple Inheritance
- **Concept**: One class inherits from multiple parent classes
- **Languages**: C++ supports it, Java does not (but supports multiple interface implementation)
- **Challenge**: Diamond problem (ambiguity when two parents have same method)

##### Multilevel Inheritance
- **Concept**: Chain of inheritance (A → B → C)
- **Example**: Vehicle → Car → SportsCar
- **Benefits**: Gradual specialization

##### Hierarchical Inheritance
- **Concept**: Multiple classes inherit from one parent class
- **Example**: Animal → Dog, Cat, Bird
- **Benefits**: Common functionality in parent class

### Polymorphism: Compile-Time (Overloading), Runtime (Overriding)

#### Definition
- **Polymorphism**: Ability of an object to take multiple forms
- **Purpose**: Same interface for different underlying data types
- **Types**: Compile-time (static) and Runtime (dynamic)

#### Compile-Time Polymorphism (Method Overloading)
- **Concept**: Multiple methods with same name but different parameters
- **Differentiation**: Based on number, type, or order of parameters
- **Resolution**: At compile time
- **Example**:
```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }
    
    public double add(double a, double b) {
        return a + b;
    }
    
    public int add(int a, int b, int c) {
        return a + b + c;
    }
}
```

#### Runtime Polymorphism (Method Overriding)
- **Concept**: Child class provides specific implementation of parent method
- **Keyword**: virtual (C#), virtual/override (C++), automatic in Java
- **Resolution**: At runtime using virtual function tables
- **Example**:
```java
class Animal {
    public void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Dog barks");
    }
}
```

### Abstraction: Abstract Classes, Interfaces

#### Definition
- **Abstraction**: Hiding complex implementation details while showing only essential features
- **Purpose**: Reduce complexity and increase efficiency
- **Implementation**: Abstract classes and interfaces

#### Abstract Classes
- **Definition**: Class that cannot be instantiated
- **Purpose**: Base class with common functionality
- **Features**:
  - Can contain abstract and concrete methods
  - Can have constructors, fields, and static methods
  - Subclass must implement abstract methods (unless also abstract)
- **Example**:
```java
abstract class Shape {
    protected String color;
    
    public abstract double calculateArea(); // Must be implemented by subclass
    
    public void setColor(String color) { // Concrete method
        this.color = color;
    }
}
```

#### Interfaces
- **Definition**: Contract specifying what methods a class must implement
- **Purpose**: Achieve loose coupling and multiple inheritance
- **Features**:
  - All methods are implicitly public and abstract (in older Java versions)
  - All fields are implicitly public, static, and final
  - Class can implement multiple interfaces
- **Example**:
```java
interface Drawable {
    void draw();
    void resize();
}

class Circle implements Drawable {
    @Override
    public void draw() {
        System.out.println("Drawing circle");
    }
    
    @Override
    public void resize() {
        System.out.println("Resizing circle");
    }
}
```

### Composition and Aggregation

#### Composition
- **Definition**: "Has-a" relationship where child cannot exist independently
- **Characteristics**: Strong relationship, life cycle dependency
- **Example**: House has Rooms; if House is destroyed, Rooms are destroyed
- **Code Example**:
```java
class Room {
    private String roomName;
    
    public Room(String name) {
        this.roomName = name;
    }
}

class House {
    private Room[] rooms; // House "owns" rooms
    
    public House() {
        this.rooms = new Room[5]; // Create rooms as part of house
        for (int i = 0; i < 5; i++) {
            rooms[i] = new Room("Room " + (i+1));
        }
    }
}
```

#### Aggregation
- **Definition**: "Has-a" relationship where child can exist independently
- **Characteristics**: Weak relationship, no life cycle dependency
- **Example**: Department has Professors; professors can exist without department
- **Code Example**:
```java
class Professor {
    private String name;
    
    public Professor(String name) {
        this.name = name;
    }
}

class Department {
    private Professor[] professors; // Department "uses" professors
    
    public Department(Professor[] profs) {
        this.professors = profs; // References to existing professors
    }
}
```

## Classes and Objects

### Class Members: Instance vs Static

#### Instance Members
- **Definition**: Belong to specific instance of class
- **Characteristics**:
  - Each object has its own copy
  - Created when object is instantiated
  - Accessed using object reference
- **Example**:
```java
class Student {
    private String name; // Instance variable
    private int age;     // Instance variable
    
    public void setName(String name) { // Instance method
        this.name = name;
    }
}
```

#### Static Members
- **Definition**: Belong to class itself, not to any specific instance
- **Characteristics**:
  - Shared among all instances
  - Created when class is loaded
  - Accessed using class name
- **Example**:
```java
class Student {
    private String name;
    private static int studentCount = 0; // Static variable
    
    public Student(String name) {
        this.name = name;
        studentCount++; // Increment for each new student
    }
    
    public static int getStudentCount() { // Static method
        return studentCount;
    }
}
```

### Constructors: Default, Parameterized, Copy, Move

#### Default Constructor
- **Definition**: Constructor with no parameters
- **Automatic Generation**: Compiler creates if no constructor is defined
- **Purpose**: Initialize object with default values
- **Example**:
```java
class Rectangle {
    private double width, height;
    
    public Rectangle() { // Default constructor
        this.width = 1.0;
        this.height = 1.0;
    }
}
```

#### Parameterized Constructor
- **Definition**: Constructor with parameters
- **Purpose**: Initialize object with specific values
- **Example**:
```java
class Rectangle {
    private double width, height;
    
    public Rectangle(double width, double height) { // Parameterized constructor
        this.width = width;
        this.height = height;
    }
}
```

#### Copy Constructor
- **Definition**: Constructor that creates object by copying another object
- **Languages**: C++ has built-in support; Java typically uses copy methods
- **Purpose**: Create exact copy of existing object
- **C++ Example**:
```cpp
class Rectangle {
    private:
        double width, height;
    public:
        Rectangle(const Rectangle &other) { // Copy constructor
            this->width = other.width;
            this->height = other.height;
        }
};
```

#### Move Constructor (C++)
- **Definition**: Transfer resources from temporary object to new object
- **Purpose**: Optimize performance by avoiding unnecessary copying
- **C++ Example**:
```cpp
class Rectangle {
    private:
        double *data;
    public:
        Rectangle(Rectangle &&other) noexcept { // Move constructor
            this->data = other.data;
            other.data = nullptr; // Transfer ownership
        }
};
```

### Destructors and Object Lifecycle

#### Destructors (C++)
- **Definition**: Special method called when object is destroyed
- **Purpose**: Clean up resources (memory, files, connections)
- **Automatic Invocation**: Called automatically when object goes out of scope
- **Example**:
```cpp
class FileHandler {
    private:
        FILE* filePtr;
    public:
        FileHandler(const char* filename) {
            filePtr = fopen(filename, "r");
        }
        
        ~FileHandler() { // Destructor
            if (filePtr) {
                fclose(filePtr);
            }
        }
};
```

#### Object Lifecycle in Java/C#
- **Creation**: Constructor called during instantiation
- **Usage**: Object exists and can be accessed
- **Garbage Collection**: Automatic cleanup when no references exist
- **Finalization**: Optional cleanup method (finalize in Java, finalizers in C#)

### Access Modifiers: Public, Private, Protected

#### Public
- **Access**: Everywhere (within class, subclasses, other packages)
- **Use Case**: Methods and fields that need to be accessible externally
- **Example**: public void calculateArea()

#### Private
- **Access**: Within the same class only
- **Use Case**: Internal implementation details
- **Example**: private double radius;

#### Protected
- **Access**: Within class, subclasses, and same package
- **Use Case**: Members that should be accessible to subclasses
- **Example**: protected String name;

#### Package-Private (Default in Java)
- **Access**: Within same package only
- **Use Case**: Package-level encapsulation
- **Example**: void displayInfo() (no modifier)

## Advanced OOP

### Virtual Functions and Dynamic Binding

#### Virtual Functions
- **Definition**: Member functions that can be overridden in derived classes
- **Purpose**: Enable polymorphic behavior
- **Implementation**: Virtual keyword in C++, automatic in Java
- **Example**:
```cpp
class Shape {
    public:
        virtual double calculateArea() = 0; // Pure virtual function
        virtual void display() {
            cout << "Shape" << endl;
        }
};

class Circle : public Shape {
    public:
        double calculateArea() override { // Override virtual function
            return 3.14 * radius * radius;
        }
};
```

#### Dynamic Binding
- **Definition**: Method to call is determined at runtime
- **Mechanism**: Virtual function table (vtable)
- **Contrast**: Static binding (compile-time) vs dynamic binding (runtime)
- **Benefit**: Enables polymorphism

### Static and Dynamic Polymorphism

#### Static Polymorphism
- **Definition**: Polymorphism resolved at compile time
- **Implementation**: Method overloading, operator overloading, templates/generics
- **Performance**: Faster (no runtime overhead)
- **Example**:
```cpp
// Method overloading (static polymorphism)
void print(int value) { cout << "Integer: " << value << endl; }
void print(double value) { cout << "Double: " << value << endl; }
void print(string value) { cout << "String: " << value << endl; }
```

#### Dynamic Polymorphism
- **Definition**: Polymorphism resolved at runtime
- **Implementation**: Method overriding, virtual functions
- **Performance**: Slight overhead due to runtime resolution
- **Example**:
```java
Shape shape = new Circle(); // Reference type is Shape, object type is Circle
shape.calculateArea(); // Calls Circle's calculateArea() at runtime
```

### Operator Overloading

#### Definition
- **Concept**: Define custom behavior for operators on user-defined types
- **Languages**: C++ has extensive support; Java has limited support
- **Purpose**: Make user-defined types behave like built-in types

#### C++ Example
```cpp
class Complex {
    private:
        double real, imag;
    public:
        Complex(double r = 0, double i = 0) : real(r), imag(i) {}
        
        // Operator overloading
        Complex operator+(const Complex& other) {
            return Complex(real + other.real, imag + other.imag);
        }
        
        Complex operator*(const Complex& other) {
            return Complex(
                real * other.real - imag * other.imag,
                real * other.imag + imag * other.real
            );
        }
        
        bool operator==(const Complex& other) {
            return (real == other.real && imag == other.imag);
        }
};
```

### Exception Handling Mechanisms

#### Exception Handling Components
- **Try**: Block where exception might occur
- **Catch**: Block to handle specific exceptions
- **Finally**: Block that executes regardless of exception (in languages that support it)

#### Java/C# Example
```java
public void readFile(String filename) {
    try {
        FileReader file = new FileReader(filename);
        BufferedReader reader = new BufferedReader(file);
        // Process file
    } catch (FileNotFoundException e) {
        System.out.println("File not found: " + e.getMessage());
    } catch (IOException e) {
        System.out.println("IO error: " + e.getMessage());
    } finally {
        // Cleanup code that always executes
    }
}
```

#### C++ Example
```cpp
#include <iostream>
#include <stdexcept>

void divide(double a, double b) {
    if (b == 0) {
        throw std::invalid_argument("Division by zero");
    }
    std::cout << a / b << std::endl;
}

int main() {
    try {
        divide(10, 0);
    } catch (const std::exception& e) {
        std::cout << "Exception caught: " << e.what() << std::endl;
    }
    return 0;
}
```

### Generic Programming and Templates

#### Generic Programming
- **Definition**: Writing code that works with any data type
- **Purpose**: Code reusability, type safety
- **Implementation**: Templates (C++), Generics (Java/C#)

#### C++ Templates
```cpp
template <typename T>
class Stack {
    private:
        T* data;
        int top;
        int capacity;
    public:
        Stack(int cap) : capacity(cap), top(-1) {
            data = new T[capacity];
        }
        
        void push(T value) {
            if (top < capacity - 1) {
                data[++top] = value;
            }
        }
        
        T pop() {
            if (top >= 0) {
                return data[top--];
            }
            throw std::out_of_range("Stack is empty");
        }
};
```

#### Java Generics
```java
public class Stack<T> {
    private T[] data;
    private int top;
    private int capacity;
    
    @SuppressWarnings("unchecked")
    public Stack(int cap) {
        this.capacity = cap;
        this.top = -1;
        this.data = (T[]) new Object[capacity];
    }
    
    public void push(T value) {
        if (top < capacity - 1) {
            data[++top] = value;
        }
    }
    
    public T pop() {
        if (top >= 0) {
            return data[top--];
        }
        throw new RuntimeException("Stack is empty");
    }
}
```

## Design Patterns

### Creational: Singleton, Factory, Builder, Prototype

#### Singleton Pattern
- **Purpose**: Ensure only one instance of a class exists
- **Implementation**: Private constructor, static instance
- **Use Cases**: Logging, Configuration settings, Database connection pool
- **Example**:
```java
public class Singleton {
    private static Singleton instance;
    
    private Singleton() {} // Private constructor
    
    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
```

#### Factory Pattern
- **Purpose**: Create objects without exposing creation logic
- **Implementation**: Factory method that returns objects
- **Use Cases**: Creating different types of objects based on parameters
- **Example**:
```java
abstract class Shape {
    abstract void draw();
}

class Circle extends Shape {
    void draw() { System.out.println("Drawing Circle"); }
}

class Rectangle extends Shape {
    void draw() { System.out.println("Drawing Rectangle"); }
}

class ShapeFactory {
    public static Shape createShape(String type) {
        if (type.equalsIgnoreCase("circle")) {
            return new Circle();
        } else if (type.equalsIgnoreCase("rectangle")) {
            return new Rectangle();
        }
        return null;
    }
}
```

#### Builder Pattern
- **Purpose**: Construct complex objects step by step
- **Implementation**: Separate builder class with fluent interface
- **Use Cases**: Creating objects with many optional parameters
- **Example**:
```java
class Pizza {
    private String dough;
    private String sauce;
    private String topping;
    
    private Pizza(Builder builder) {
        this.dough = builder.dough;
        this.sauce = builder.sauce;
        this.topping = builder.topping;
    }
    
    public static class Builder {
        private String dough;
        private String sauce;
        private String topping;
        
        public Builder setDough(String dough) {
            this.dough = dough;
            return this;
        }
        
        public Builder setSauce(String sauce) {
            this.sauce = sauce;
            return this;
        }
        
        public Builder setTopping(String topping) {
            this.topping = topping;
            return this;
        }
        
        public Pizza build() {
            return new Pizza(this);
        }
    }
}
```

#### Prototype Pattern
- **Purpose**: Create new objects by cloning existing objects
- **Implementation**: Clone method in base class
- **Use Cases**: When creating objects is expensive
- **Example**:
```java
interface Prototype {
    Prototype clone();
}

class Employee implements Prototype {
    private String name;
    private int age;
    
    public Employee(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    @Override
    public Employee clone() {
        return new Employee(this.name, this.age);
    }
}
```

### Structural: Adapter, Bridge, Composite, Decorator, Facade

#### Adapter Pattern
- **Purpose**: Allow incompatible interfaces to work together
- **Implementation**: Wrapper that converts interface
- **Use Cases**: Integrating legacy code, third-party libraries
- **Example**:
```java
interface MediaPlayer {
    void play(String audioType, String fileName);
}

class AudioPlayer implements MediaPlayer {
    public void play(String audioType, String fileName) {
        if(audioType.equalsIgnoreCase("mp3")) {
            System.out.println("Playing mp3 file: " + fileName);
        } else {
            // MP4 and VLC players needed for other formats
            AdvancedMediaPlayer advancedMusicPlayer = 
                new Mp4Player();
            advancedMusicPlayer.playMp4(fileName);
        }
    }
}
```

#### Bridge Pattern
- **Purpose**: Separate abstraction from implementation
- **Implementation**: Abstraction and implementation hierarchies
- **Use Cases**: Platform independence, switching implementations at runtime
- **Example**:
```java
interface Color {
    void applyColor();
}

class RedColor implements Color {
    public void applyColor() {
        System.out.println("red color");
    }
}

abstract class Shape {
    protected Color color;
    
    protected Shape(Color color) {
        this.color = color;
    }
    
    abstract void applyColor();
}

class Triangle extends Shape {
    public Triangle(Color color) {
        super(color);
    }
    
    @Override
    void applyColor() {
        System.out.print("Triangle filled with ");
        color.applyColor();
    }
}
```

#### Composite Pattern
- **Purpose**: Compose objects into tree structures
- **Implementation**: Component interface for both leaf and composite objects
- **Use Cases**: Representing part-whole hierarchies
- **Example**:
```java
interface Component {
    void showPrice();
}

class Leaf implements Component {
    private int price;
    private String name;
    
    public Leaf(String name, int price) {
        this.name = name;
        this.price = price;
    }
    
    public void showPrice() {
        System.out.println(name + ": " + price);
    }
}

class Composite implements Component {
    private List<Component> components = new ArrayList<>();
    
    public void add(Component component) {
        components.add(component);
    }
    
    public void showPrice() {
        for (Component component : components) {
            component.showPrice();
        }
    }
}
```

#### Decorator Pattern
- **Purpose**: Add functionality to objects dynamically
- **Implementation**: Wrapper objects that enhance original object
- **Use Cases**: Adding features without inheritance
- **Example**:
```java
interface Coffee {
    String getDescription();
    double getCost();
}

class SimpleCoffee implements Coffee {
    public String getDescription() {
        return "Simple coffee";
    }
    
    public double getCost() {
        return 2.0;
    }
}

abstract class CoffeeDecorator implements Coffee {
    protected Coffee decoratedCoffee;
    
    public CoffeeDecorator(Coffee coffee) {
        this.decoratedCoffee = coffee;
    }
    
    public String getDescription() {
        return decoratedCoffee.getDescription();
    }
    
    public double getCost() {
        return decoratedCoffee.getCost();
    }
}

class MilkDecorator extends CoffeeDecorator {
    public MilkDecorator(Coffee coffee) {
        super(coffee);
    }
    
    public String getDescription() {
        return super.getDescription() + ", milk";
    }
    
    public double getCost() {
        return super.getCost() + 0.5;
    }
}
```

#### Facade Pattern
- **Purpose**: Provide simplified interface to complex subsystem
- **Implementation**: Single class that delegates to subsystem classes
- **Use Cases**: Simplifying complex APIs, providing unified interface
- **Example**:
```java
class CPU {
    public void freeze() { /* ... */ }
    public void jump(long position) { /* ... */ }
    public void execute() { /* ... */ }
}

class Memory {
    public void load(long position, byte[] data) { /* ... */ }
}

class HardDrive {
    public byte[] read(long lba, int size) { /* ... */ }
}

class ComputerFacade {
    private CPU cpu;
    private Memory memory;
    private HardDrive hardDrive;
    
    public ComputerFacade() {
        this.cpu = new CPU();
        this.memory = new Memory();
        this.hardDrive = new HardDrive();
    }
    
    public void start() {
        cpu.freeze();
        memory.load(0, hardDrive.read(0, 1024));
        cpu.jump(0);
        cpu.execute();
    }
}
```

### Behavioral: Observer, Strategy, Command, Iterator, Template Method

#### Observer Pattern
- **Purpose**: Define dependency between objects so that when one changes, others are notified
- **Implementation**: Subject maintains list of observers
- **Use Cases**: Event handling systems, Model-View architecture
- **Example**:
```java
import java.util.*;

interface Observer {
    void update(String message);
}

class NewsAgency {
    private String news;
    private List<Observer> observers = new ArrayList<>();
    
    public void addObserver(Observer observer) {
        observers.add(observer);
    }
    
    public void removeObserver(Observer observer) {
        observers.remove(observer);
    }
    
    public void setNews(String news) {
        this.news = news;
        notifyObservers();
    }
    
    private void notifyObservers() {
        for (Observer observer : observers) {
            observer.update(news);
        }
    }
}

class NewsChannel implements Observer {
    private String news;
    
    public void update(String news) {
        this.news = news;
        System.out.println("NewsChannel received news: " + news);
    }
}
```

#### Strategy Pattern
- **Purpose**: Define family of algorithms, encapsulate each one, make them interchangeable
- **Implementation**: Strategy interface with multiple implementations
- **Use Cases**: Different algorithms for same operation
- **Example**:
```java
interface PaymentStrategy {
    void pay(int amount);
}

class CreditCardStrategy implements PaymentStrategy {
    private String name;
    private String cardNumber;
    
    public CreditCardStrategy(String name, String cardNumber) {
        this.name = name;
        this.cardNumber = cardNumber;
    }
    
    public void pay(int amount) {
        System.out.println(amount + " paid with credit card");
    }
}

class ShoppingCart {
    private List<Item> items;
    private PaymentStrategy paymentStrategy;
    
    public void setPaymentStrategy(PaymentStrategy strategy) {
        this.paymentStrategy = strategy;
    }
    
    public void checkout() {
        int total = calculateTotal();
        paymentStrategy.pay(total);
    }
}
```

#### Command Pattern
- **Purpose**: Encapsulate request as an object
- **Implementation**: Command interface with execute method
- **Use Cases**: Undo/redo functionality, transaction systems
- **Example**:
```java
interface Command {
    void execute();
    void undo();
}

class Light {
    private boolean isOn = false;
    
    public void turnOn() {
        isOn = true;
        System.out.println("Light is on");
    }
    
    public void turnOff() {
        isOn = false;
        System.out.println("Light is off");
    }
}

class TurnOnCommand implements Command {
    private Light light;
    
    public TurnOnCommand(Light light) {
        this.light = light;
    }
    
    public void execute() {
        light.turnOn();
    }
    
    public void undo() {
        light.turnOff();
    }
}

class RemoteControl {
    private Command command;
    
    public void setCommand(Command command) {
        this.command = command;
    }
    
    public void pressButton() {
        command.execute();
    }
    
    public void pressUndo() {
        command.undo();
    }
}
```

#### Iterator Pattern
- **Purpose**: Provide way to access elements of aggregate object sequentially
- **Implementation**: Iterator interface with methods like hasNext() and next()
- **Use Cases**: Traversing collections, hiding implementation details
- **Example**:
```java
interface Iterator<T> {
    boolean hasNext();
    T next();
}

interface Container {
    Iterator<String> createIterator();
}

class NameRepository implements Container {
    public String[] names = {"Robert", "John", "Julie", "Lora"};
    
    public Iterator<String> createIterator() {
        return new NameIterator();
    }
    
    private class NameIterator implements Iterator<String> {
        int index;
        
        public boolean hasNext() {
            return index < names.length;
        }
        
        public String next() {
            if (this.hasNext()) {
                return names[index++];
            }
            return null;
        }
    }
}
```

#### Template Method Pattern
- **Purpose**: Define skeleton of algorithm in base class
- **Implementation**: Abstract methods that subclasses implement
- **Use Cases**: Frameworks, algorithms with common structure
- **Example**:
```java
abstract class Game {
    abstract void initialize();
    abstract void startPlay();
    abstract void endPlay();
    
    // Template method
    public final void play() {
        initialize();
        startPlay();
        endPlay();
    }
}

class Cricket extends Game {
    void endPlay() {
        System.out.println("Cricket Game Finished!");
    }
    
    void initialize() {
        System.out.println("Cricket Game Initialized! Start playing.");
    }
    
    void startPlay() {
        System.out.println("Cricket Game Started. Enjoy the game!");
    }
}
```

## SOLID Principles

### Single Responsibility Principle

#### Definition
- **Concept**: A class should have only one reason to change
- **Purpose**: Increase maintainability and reduce coupling
- **Benefit**: Makes code easier to understand, modify, and test

#### Violation Example
```java
class Employee {
    private String name;
    private double salary;
    
    // Violates SRP - handles business logic AND database operations
    public void calculatePay() { /* ... */ }
    public void saveToDatabase() { /* ... */ }
    public void generateReport() { /* ... */ }
}
```

#### Corrected Example
```java
class Employee {
    private String name;
    private double salary;
    
    public void calculatePay() { /* ... */ }
}

class EmployeeRepository {
    public void save(Employee emp) { /* ... */ }
    public Employee findById(int id) { /* ... */ }
}

class EmployeeReportGenerator {
    public void generateReport(Employee emp) { /* ... */ }
}
```

### Open/Closed Principle

#### Definition
- **Concept**: Software entities should be open for extension but closed for modification
- **Purpose**: Extend functionality without changing existing code
- **Benefit**: Reduces risk of breaking existing functionality

#### Implementation Techniques
- **Inheritance**: Extend classes to add new functionality
- **Composition**: Combine objects to achieve new behaviors
- **Strategy Pattern**: Inject different algorithms at runtime

#### Example
```java
// Closed for modification
abstract class Shape {
    abstract double calculateArea();
}

// Open for extension
class Circle extends Shape {
    private double radius;
    
    public Circle(double radius) {
        this.radius = radius;
    }
    
    @Override
    double calculateArea() {
        return Math.PI * radius * radius;
    }
}

class Rectangle extends Shape {
    private double width, height;
    
    public Rectangle(double width, double height) {
        this.width = width;
        this.height = height;
    }
    
    @Override
    double calculateArea() {
        return width * height;
    }
}

// Area calculator doesn't need modification for new shapes
class AreaCalculator {
    public double calculateTotalArea(List<Shape> shapes) {
        return shapes.stream().mapToDouble(Shape::calculateArea).sum();
    }
}
```

### Liskov Substitution Principle

#### Definition
- **Concept**: Objects of a superclass should be replaceable with objects of its subclasses
- **Purpose**: Ensure derived classes extend base class without changing behavior
- **Benefit**: Maintains correctness when using inheritance

#### Violation Example
```java
class Rectangle {
    protected int width, height;
    
    public void setWidth(int width) { this.width = width; }
    public void setHeight(int height) { this.height = height; }
    public int getArea() { return width * height; }
}

class Square extends Rectangle {
    // Violates LSP - setting width affects height
    @Override
    public void setWidth(int width) {
        this.width = width;
        this.height = width; // Forces square shape
    }
    
    @Override
    public void setHeight(int height) {
        this.width = height;
        this.height = height; // Forces square shape
    }
}
```

#### Corrected Example
```java
abstract class Shape {
    public abstract double calculateArea();
}

class Rectangle extends Shape {
    protected int width, height;
    
    public Rectangle(int width, int height) {
        this.width = width;
        this.height = height;
    }
    
    @Override
    public double calculateArea() {
        return width * height;
    }
}

class Square extends Shape {
    private int side;
    
    public Square(int side) {
        this.side = side;
    }
    
    @Override
    public double calculateArea() {
        return side * side;
    }
}
```

### Interface Segregation Principle

#### Definition
- **Concept**: Clients should not be forced to depend on interfaces they don't use
- **Purpose**: Create focused, cohesive interfaces
- **Benefit**: Reduces coupling and increases flexibility

#### Violation Example
```java
interface Worker {
    void work();
    void eat();
    void sleep();
}

class HumanWorker implements Worker {
    public void work() { System.out.println("Human working"); }
    public void eat() { System.out.println("Human eating"); }
    public void sleep() { System.out.println("Human sleeping"); }
}

class Robot implements Worker {
    public void work() { System.out.println("Robot working"); }
    public void eat() { /* Robots don't eat - violates ISP */ }
    public void sleep() { /* Robots don't sleep - violates ISP */ }
}
```

#### Corrected Example
```java
interface Workable {
    void work();
}

interface Eatable {
    void eat();
}

interface Sleepable {
    void sleep();
}

class HumanWorker implements Workable, Eatable, Sleepable {
    public void work() { System.out.println("Human working"); }
    public void eat() { System.out.println("Human eating"); }
    public void sleep() { System.out.println("Human sleeping"); }
}

class Robot implements Workable {
    public void work() { System.out.println("Robot working"); }
}
```

### Dependency Inversion Principle

#### Definition
- **Concept**: High-level modules should not depend on low-level modules; both should depend on abstractions
- **Abstractions should not depend on details; details should depend on abstractions**
- **Purpose**: Reduce coupling between high and low-level modules
- **Benefit**: Makes code more modular and testable

#### Violation Example
```java
class EmailService {
    public void sendEmail(String message) {
        // Send email implementation
    }
}

// High-level module depends directly on low-level module
class NotificationManager {
    private EmailService emailService = new EmailService();
    
    public void notify(String message) {
        emailService.sendEmail(message);
    }
}
```

#### Corrected Example
```java
interface MessageService {
    void sendMessage(String message);
}

class EmailService implements MessageService {
    public void sendMessage(String message) {
        // Send email implementation
    }
}

class SMSService implements MessageService {
    public void sendMessage(String message) {
        // Send SMS implementation
    }
}

// High-level module depends on abstraction
class NotificationManager {
    private MessageService messageService;
    
    public NotificationManager(MessageService messageService) {
        this.messageService = messageService;
    }
    
    public void notify(String message) {
        messageService.sendMessage(message);
    }
}
```

## UML Diagrams

### Class Diagrams, Object Diagrams

#### Class Diagrams
- **Purpose**: Show structure of system including classes, attributes, methods, and relationships
- **Elements**:
  - **Class**: Rectangular box with class name, attributes, and methods
  - **Visibility**: + (public), - (private), # (protected), ~ (package)
  - **Relationships**: Association, Inheritance, Dependency, Realization

#### Class Diagram Notation
```
┌─────────────────┐
│   ClassName     │
├─────────────────┤
│- attribute1: Type│
│# attribute2: Type│
│+ attribute3: Type│
├─────────────────┤
│- method1(): Type │
│+ method2(param):│
│  Type           │
└─────────────────┘
```

#### Object Diagrams
- **Purpose**: Show instances of classes and their relationships at specific point in time
- **Similar to**: Class diagrams but show actual objects with values
- **Use Cases**: Illustrate specific scenarios, debugging

### Sequence Diagrams, Activity Diagrams

#### Sequence Diagrams
- **Purpose**: Show interactions between objects in chronological order
- **Elements**:
  - **Lifelines**: Vertical dashed lines representing objects
  - **Messages**: Arrows showing method calls
  - **Activation boxes**: Rectangles showing when object is active
- **Types of Messages**: Synchronous, asynchronous, return

#### Activity Diagrams
- **Purpose**: Model workflow and business processes
- **Elements**:
  - **Initial node**: Black circle (start)
  - **Activity**: Rounded rectangles
  - **Decision node**: Diamond shape
  - **Merge node**: Diamond shape
  - **Fork/Join**: Thick bars
  - **Final node**: Circle with thick border (end)

### Use Case Diagrams

#### Purpose
- **Show**: Functional requirements from user perspective
- **Actors**: External entities interacting with system
- **Use Cases**: Specific functionalities provided by system
- **Relationships**: Include, Extend, Generalization

#### Elements
- **Actor**: Stick figure representing user or external system
- **Use Case**: Oval representing specific functionality
- **System Boundary**: Rectangle containing use cases
- **Relationships**:
  - **Association**: Line connecting actor to use case
  - **Include**: <<include>> dependency
  - **Extend**: <<extend>> conditional dependency
  - **Generalization**: Arrow with hollow triangle

## Summary

This chapter covered essential Object-Oriented Programming concepts that form the foundation of modern software development. Understanding these concepts is crucial for evaluating software solutions, understanding system architecture, and making informed decisions about development methodologies. The next chapter will focus on software development methodologies.

## Key Takeaways

1. OOP principles (encapsulation, inheritance, polymorphism, abstraction) provide structure for organizing code
2. Design patterns offer proven solutions to common design problems
3. SOLID principles guide the creation of maintainable and scalable code
4. UML diagrams provide visual representation of system design
5. Understanding OOP concepts helps in technology evaluation and system architecture decisions

## Practice Questions

1. What is the difference between method overloading and method overriding?
2. Explain the Single Responsibility Principle with an example.
3. What is the difference between composition and aggregation?
4. Name three design patterns and their purposes.
5. What does the "D" in SOLID stand for and what does it mean?

## Answers

1. Method overloading occurs at compile time with multiple methods of same name but different parameters in the same class, while method overriding occurs at runtime when a subclass provides specific implementation of a parent method.
2. The Single Responsibility Principle states that a class should have only one reason to change. For example, instead of having an Employee class that calculates pay, saves to database, and generates reports, these should be separated into different classes, each with one responsibility.
3. In composition, the child cannot exist independently of the parent (strong relationship), while in aggregation, the child can exist independently (weak relationship).
4. Singleton (ensure only one instance), Factory (create objects without exposing creation logic), Observer (define dependency between objects).
5. The "D" stands for Dependency Inversion Principle, which states that high-level modules should not depend on low-level modules; both should depend on abstractions.