# Assignment 1: Smart Home Device Design Patterns

This repository showcases a Java-based solution for implementing the **Abstract Factory** and **Factory Method** design patterns. The goal is to build a scalable system for creating smart home devices, such as bulbs and locks, from different brands. This design effectively separates the creation process from the client code, making the system flexible and easy to extend.

---

### Key Concepts

#### Abstract Factory
The **Abstract Factory** pattern provides an interface for creating families of related objects without specifying their concrete classes. In this project, the `DeviceFactory` interface acts as the abstract factory, defining methods to create different types of smart devices (`createLightBulb()` and `createSmartLock()`). This pattern ensures that a client (like `Main.java`) is decoupled from the specific brands, allowing it to work with any `DeviceFactory` implementation. 

#### Factory Method
The **Factory Method** pattern defines an interface for creating a single object but lets subclasses decide which class to instantiate. Here, the `createLightBulb()` and `createSmartLock()` methods within the `DeviceFactory` interface are factory methods. Each concrete factory, like `BrandAlphaFactory`, implements these methods to produce a specific product (e.g., `BrandAlphaBulb`). This pattern makes it simple to add new device types or brands without changing existing code.

---

### Repository Structure

This project is organized to clearly separate the core design pattern implementation from the test driver.

* `sourcefiles/`: Contains all the core Java classes for the design patterns.
    * `DeviceFactory.java`: The abstract factory interface.
    * `BrandAlphaFactory.java`, `BrandBetaFactory.java`: Concrete factory implementations for specific brands.
    * `LightBulb.java`, `SmartLock.java`: Abstract product classes defining the common interface for all devices.
    * `BrandAlphaBulb.java`, `BrandAlphaLock.java`: Concrete product implementations for **Brand Alpha**.
    * `BrandBetaBulb.java`, `BrandBetaLock.java`: Concrete product implementations for **Brand Beta**.
* `testfiles/`: Includes the test driver to demonstrate the system's functionality.
    * `Main.java`: The primary class used to test and showcase the design.

---

### UML Class Diagram


This UML diagram visualizes the project's design, illustrating how the **Abstract Factory** and **Factory Method** patterns work together. A client (`Main`) uses a `DeviceFactory` to create abstract products (`LightBulb`, `SmartLock`) without needing to know the concrete product classes.
---

### Execution and Demonstration

The `Main.java` class demonstrates the system's flexibility by creating devices from different brands. To run the program:

1.  Compile all the Java files:
    ```bash
    javac src/*.java tests/*.java
    ```
2.  Run the main class from the command line:
    ```bash
    java tests.Main
    ```

#### Example Output:
The program's output will confirm that devices from both Brand Alpha and Brand Beta are successfully created and configured, demonstrating that the design effectively handles different product families.

* **Brand Alpha Bulb**: The `BrandAlphaFactory` is used to create a `BrandAlphaBulb` object. The program then simulates setting its power usage.
* **Brand Beta Lock**: The `BrandBetaFactory` is used to create a `BrandBetaLock` object. The program then simulates setting its battery consumption.

---

### Contribution and Feedback

Feel free to explore the code and provide feedback. If you'd like to extend this project, consider adding a new brand, a new type of device (e.g., a smart thermostat), or implementing a different design pattern.
