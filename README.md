# ☕ Java — Explained Like Never Before

Explained like never before -> Java from scratch to advanced — core concepts explained with real-life examples. A structured learning repo covering OOP, Collections, Multithreading & more.

---

## Table of Contents

- [Basics](#basics) 🧭
  - [What is Java?](#what-is-java) 💡
  - [How Java works](#how-java-works) ⚙️
  - [How to install Java](#how-to-install-java) ⬇️
  - [What is OOP?](#what-is-oop) 🧩
  - [Class — The Blueprint](#class--the-blueprint) 🏗️
  - [Object — The Real Thing](#object--the-real-thing) 🏠
  - [How to Create an Object](#how-to-create-an-object) 🧱
- [Java OOP — Common Mistake: Class with Parameters](#-java-oop---common-mistake-class-with-parameters-❗) ⚠️
- [Install IntelliJ and run your first Java program](#install-intellij-and-run-your-first-java-program) 🛠️
- [4 pillars of OOP](#4-pillars-of-oop-🧩) 🧩
  - [Encapsulation (1st Pillar)](#-java-oop---encapsulation-1st-pillar-🔐) 🔐
  - [Inheritance (2nd Pillar)](#-java-oop---inheritance-2nd-pillar-🚀) 🚀


---

## Basics

<a id="basics"></a>

<a id="what-is-java"></a>
## What is Java? 💡

Java is a programming language used to tell computers what to do.

Think like this:
- You write instructions = Java code
- Computer understands them after conversion

Java is also a platform because it gives you tools to turn code into a running program.

<a id="how-java-works"></a>
## How Java works ⚙️

A Java program follows a simple process:

1. You write the code in files with .java extension.
2. The code gets compiled into bytecode, which is a special format that works on any computer.
3. The JVM runs the bytecode by turning it into instructions that your specific computer can understand, so the program works on Windows, Mac, Linux, etc.


| Pipeline | Description |
|---:|---|
| 📄 .java (source code) <br> ↓ <br> 🛠️ javac (compiler) <br> ↓ <br> 📦 .class (bytecode) <br> ↓ <br> 🖥️ JVM (interpreter + JIT) <br> ↓ <br> ⚙️ Machine Code (runs on OS) | .java: human-readable source you write. <br> javac: compiles source into bytecode. <br> .class: platform-independent bytecode. <br> JVM: loads bytecode, interprets and JIT-compiles hot code. <br> Machine Code: native CPU instructions executed by the OS/hardware. |

## JDK, JRE, JVM — what are they? 🧰

- **JVM** 🖥️ = Java Virtual Machine
  - It runs Java bytecode.
  - It is the part that works on Windows, Mac, or Linux.
  - JVM is like the machine that understands the code.

- **JRE** 🍽️ = Java Runtime Environment
  - It has the JVM plus the standard Java libraries.
  - It is enough to run Java programs.
  - JRE is like the kitchen with the stove and ingredients.

- **JDK** 🧰 = Java Development Kit
  - It has the JRE plus tools to write and compile Java code.
  - It is what you need to make Java programs.
  - JDK is like a full kitchen with tools, stove, ingredients, and recipe books.

Important tools in the JDK:
- `javac` — compiler that turns `.java` code into `.class` bytecode
- `java` — launcher that starts the JVM and runs the bytecode
- `jar` — packages Java files into one archive

<a id="how-to-install-java"></a>
## How to install Java ⬇️

When someone says “install Java,” they usually mean “install the JDK.” ✅

- On Mac:
  - Use Homebrew: `brew install --cask temurin` 🖥️
- On Windows:
  - Download an OpenJDK package such as Eclipse Temurin 🪟
- On Linux:
  - Use the package manager, for example: `sudo apt install openjdk-17-jdk` 🐧

After installation, check:

```bash
java -version
javac -version
```

<a id="what-is-oop"></a>
## What is OOP? 🧩

OOP stands for **Object Oriented Programming**.

Think of the real world — everything around you is an **object**:
- A Dog has a name, color, age → and can bark, eat, run
- A Car has a brand, color, speed → and can drive, stop, honk

Java organizes code the **same way** — using objects that have **properties** and **behaviors**.

---

## Class — The Blueprint 🏗️

<a id="class--the-blueprint"></a>

Class is a blueprint for creating objects. It defines structure (fields) and behaviour (methods) of objects.

> Think of it like a **house plan on paper**. The plan exists, but no one lives in it yet. 🏠

```java
// This is a CLASS — just a blueprint for a Dog
class Dog {

    // Properties (what the dog HAS) — empty for now, waiting to be filled
    String name;
    String color;
    int age;

    // Behaviors (what the dog CAN DO)
    void bark() {
        System.out.println(name + " says: Woof!");
    }

    void eat() {
        System.out.println(name + " is eating...");
    }
}
```

At this point, `name`, `color`, and `age` are **empty** — just waiting to be filled when we create a real dog (object).

---

## Object — The Real Thing 🏠

<a id="object--the-real-thing"></a>

An **Object** is the **actual thing** created from the blueprint.

>  The blueprint was just a plan. The **object** is the actual house built from that plan.

```java
Dog myDog1 = new Dog();   // Real dog created!
myDog1.name  = "Bruno";   // Now filling in the empty fields
myDog1.color = "Brown";
myDog1.age   = 3;

myDog1.bark(); // Bruno says: Woof!
myDog1.eat();  // Bruno is eating...
```

You can create **many objects** from the same class:

```java
Dog myDog2 = new Dog();
myDog2.name  = "Tommy";
myDog2.color = "White";
myDog2.age   = 5;

myDog2.bark(); // Tommy says: Woof!
```

---

## How to Create an Object 🧱

<a id="how-to-create-an-object"></a>

This one line confuses many beginners:

```java
Dog myDog1 = new Dog();
```

Think of it like this: "I want a Dog, name it myDog1, and make a new Dog now!"

So, Now let's break it into **3 parts**:

```
Dog        myDog1      =      new Dog();
 |            |                   |
PART 1      PART 2             PART 3
```

| Part | What it means | Simple explanation |
|------|--------------|-------------------|
| `Dog` (1st) | The **TYPE** | "I will store a Dog here" |
| `myDog1` | The **NAME** | "I'll call it myDog1" |
| `new Dog()` | Actually **BUILD** it | "Go create a real Dog now!" |

### Why is "Dog" written TWO times?

```java
Dog        myDog1  =  new   Dog();
 |                           |
"I will store              "Actually
 a Dog type"                BUILD a Dog"
```

- **First `Dog`** → Just a **promise/label** saying "this container holds a Dog"
- **Second `Dog()`** → The actual **construction** happening in memory

> Think of it like:
> - First `Dog` = "I need a Dog-sized box" (reserving space)
> - `new Dog()` = "Now actually put a Dog in it!" (real creation)

---

## Basic Java program — skeleton 💻

```java
class Dog {
    public static void main(String[] args) {
        System.out.println("Hello World"); // prints a line to console 🖨️
    }
}
```

What each part means (simple and easy to remember):

- public
  - Access modifier: "everyone can use it".
  - Think: a door labeled "public" — anyone can open it.
  - Example: public means JVM (and other code) can call this method.

- static
  - Belongs to the class itself, not to any single object.
  - Think: a factory notice on the building (one copy for all workers), not on each worker.
  - Why used here: JVM calls main without creating a Dog object, so main must be static.

- void
  - Means "this method returns nothing".

- main
  - The special method name JVM looks for as the program's starting point.
  - Think: "Main entrance" — program starts here.
  - Signature must match (name + parameters) so JVM can find it.

- String[] args
  - String[] = an array (list) of String values.
  - args = the variable name (conventionally "args"); you can name it differently.
  - Why String[]? Command-line arguments are text; there can be zero or many values, so we use an array.
  - Example: java Dog hello world
    - args[0] = "hello"
    - args[1] = "world"

- System
  - A built-in Java class that provides system-level utilities.

- out
  - A public static field inside System (System.out).
  - It's a PrintStream object that represents standard output (the console).

- println
  - A method on PrintStream that prints text and moves to a new line.
  - Think: "print line" — print this and go to the next line.

Easy-to-remember tiny story
- JVM arrives at the Main Entrance (main).
- It doesn't need a Dog object (main is static).
- It follows the public sign (method must be public).
- It looks at a list of words in the mailbag (String[] args).
- To show something, it tells System.out to println — "print a line to the console".

## Java — multi-paradigm (not pure OOP)

Java supports multiple programming styles (object-oriented, procedural, and functional) — so it's multi-paradigm. It is not a "pure" OOP language.

Why Java is NOT pure OOP and what that means:
- Primitives exist: int, boolean, double, etc. — these are not objects (they are simple values).
  - Think: not everything in Java is a "box" (object); some things are just raw values.
- Static members and methods belong to a class, not to an object instance.
  - Think: a shared sign on the building (one for all), not something every object carries.
- You can write procedural code (methods that operate on data) and use primitive-based APIs.

---

<a id="install-intellij-and-run-your-first-java-program"></a>
## Install IntelliJ and run your first Java program 🛠️

Quick overview: install IntelliJ IDEA, attach a JDK, create a project, add a class with main, then run it. ✅

1) Install IntelliJ IDEA
- Mac: Download from https://www.jetbrains.com/idea/download or use Homebrew `brew install --cask intellij-idea-ce` 💻
- Windows / Linux: Download the Community edition from JetBrains page and install.

2) Make sure JDK is available
- Option A: Install a JDK separately (recommended). Example (Mac / Linux):
  - brew install --cask temurin   (Mac) 🧩
  - sudo apt install openjdk-17-jdk   (Linux) 🐧
- Option B: Let IntelliJ download a JDK when creating a project.
- Verify on terminal:
  - java -version
  - javac -version ✅

3) Create a new Java project in IntelliJ
- File → New → Project
- Choose "Java" and pick a Project SDK:
  - If no SDK listed, click "Add SDK" → "Download JDK" (choose Temurin/OpenJDK) or point to an installed JDK path.
- Name the project (e.g., MyFirstJava) and finish.

4) Add source and a Java class
- In Project view: right-click src → New → Java Class → name it Dog
- Paste this minimal program:

```java
// filepath: /Users/mac/Documents/Java/README.md
class Dog {
    public static void main(String[] args) {
        System.out.println("Hello World"); // prints a line to console 🖨️
    }
}
```

5) Run the program
- Click the green Run icon that appears to the left of the main method, or Run → Run 'Dog'.
- Output appears in the Run tool window:
  - Hello World

6) Common tips / troubleshooting
- If IntelliJ reports "No JDK", attach/download one in Project Structure → Project SDK.
- If run button is missing, ensure your class has the correct main signature:
  - public static void main(String[] args)
- Use packages for real projects. For learning, start without a package to avoid classpath confusion.

One-liner memory aid
- Install IntelliJ → attach JDK → New Project (Java) → create Dog with main → click Run → see "Hello World".

---

# ☕ Java OOP — Common Mistake: Class with Parameters ❗

<a id="-java-oop---common-mistake-class-with-parameters-❗"></a>

---

## 📌 Scenario

Assume we have **two classes**:

1. `Test.java` → Main file (entry point)  
2. `Car.java` → Blueprint class

Both are inside the same package:

```java
package com.rcs.javalearning.datatypes;
```

---

## 🧪 Test.java (Main Class)

```java
package com.rcs.javalearning.datatypes;

public class Test {
    public static void main(String[] args){
        Car mycar1 = new Car("Buggati", "100kmp", "Black");

        mycar1.color = "Blue";
    }
}
```

---

## ❌ Car.java (Wrong Code)

```java
package com.rcs.javalearning.datatypes;

public class Car(String args1, String args2, String args3) {

    String name = args1;
    String speed = args2;
    String color = args3;

    void drive(String args){
        System.out.println(args + " is driving");
    }
}
```

---

## 🤯 Why This Code is WRONG?

### ❌ Problem 1: Class Cannot Take Parameters

```java
public class Car(String args1, String args2, String args3)
```

👉 In Java:

* A **class is just a blueprint**
* It **cannot accept parameters**

👉 Only these are allowed inside a class:

* Variables (fields)
* Methods
* Constructors

---

### ❌ Problem 2: Variables Initialized Incorrectly

```java
String name = args1;
```

👉 `args1`, `args2`, `args3` are **not defined in class scope**  
👉 They only exist if passed via a constructor

---

## 🧠 Key Concept

> ❗ Classes define structure, but **constructors initialize data**

---

## ✅ Correct Approach

---

## ✔️ Car.java (Correct Code)

```java
package com.rcs.javalearning.datatypes;

public class Car {

    String name;
    String speed;
    String color;

    // ✅ Constructor
    public Car(String args1, String args2, String args3) {
        this.name = args1;
        this.speed = args2;
        this.color = args3;
    }

    void drive(String args){
        System.out.println(args + " is driving");
    }
}
```

---

## ✔️ Test.java (Same Code Works Now)

```java
package com.rcs.javalearning.datatypes;

public class Test {
    public static void main(String[] args){
        Car mycar1 = new Car("Buggati", "100kmp", "Black");

        mycar1.color = "Blue";
    }
}
```

---

## 🔍 What Changed?

| Before ❌                      | After ✅                    |
| ----------------------------- | -------------------------- |
| Class had parameters          | Constructor has parameters |
| Variables used undefined args | Values passed properly     |
| Invalid syntax                | Valid Java structure       |

---

## 🧠 Simple Understanding

* Class = 🏠 Blueprint  
* Constructor = 🏗️ Builder

👉 You don’t pass details to blueprint  
👉 You pass details while creating object

---

## 🔁 Related: Understanding Object Data & Variables (moved here)

### 📌 Your Code

#### Test.java

```java
package com.rcs.javalearning.datatypes;

public class Test {
    public static void main(String[] args){
        Car mycar1 = new Car("Bugatti", "100kmp", "Black");
        mycar1.drive();
    }
}
```

#### Car.java

```java
package com.rcs.javalearning.datatypes;

public class Car {
    String name;
    String speed;
    String color;

    public Car(String args1, String args2, String args3){
        this.name = args1; // stored in the object
        this.speed = args2;
        this.color = args3;
    }

    void drive(){
        System.out.println(name + " is driving");
    }
}
```

---

### 🤯 Question

> We are NOT passing anything to `drive()` — then how does `"Bugatti"` appear?

### 🧠 Simple Answer

👉 `"Bugatti"` is stored inside the object when it is created.  
👉 `drive()` uses that stored value from the object.

### ⚙️ Flow

1. Object created: `Car mycar1 = new Car("Bugatti", "100kmp", "Black");`  
2. Constructor stores values: `this.name = "Bugatti";`  
3. Method uses stored value: `System.out.println(name + " is driving");`

`name` = `"Bugatti"` (from object memory)

---

### ⚡ Difference: Local vs Instance Variable (short)

- Instance variable = belongs to object, stored in object memory, accessible from instance methods.  
- Local variable = temporary, exists only during method execution.

---

## 🎯 Final Summary (for common mistakes)

* ❌ Don’t try to give parameters to a class declaration.  
* ✅ Use constructors to pass and store initial values.  
* ✅ Methods can use stored values — no need to pass them again.  
* ✅ Prefer private fields + getters/setters when controlling data (see Encapsulation section).

---

#  
<a id="4-pillars-of-oop-🧩"></a>
# <a id="-java-oop---encapsulation-1st-pillar-🔐"></a>
# <a id="encapsulation"></a>
# <a id="encapsulation-1st-pillar"></a>
# ☕ Java OOP — Encapsulation (1st Pillar)

---

## 📌 What is Encapsulation?

**Encapsulation** means:

> **Wrapping data (variables) and methods (functions) into a single unit (class) and restricting direct access to the data.**

---

## 👶 Simple Definition

👉 **“Hide the data and control how it is used.”**

---

## 🧠 Real-Life Example

Think of an **ATM Machine 🏧**

* You cannot directly access the bank balance inside
* You use methods like:

  * `checkBalance()`
  * `withdraw()`

👉 The actual data (balance) is **hidden**
👉 You interact through **controlled methods**

---

## ⚙️ Problem Without Encapsulation

Using previous example:

```java
class Car {
  String name;
  String speed;
  String color;
}
```

👉 Anyone can do:

```java
mycar1.name = null;
mycar1.speed = "-999";
```

❌ Data can be **invalid or unsafe**

---

## ✅ Applying Encapsulation

### ✔️ Car.java

```java
package com.rcs.javalearning.datatypes;

public class Car {
    private String name; //we have to make it private to that there will be no direct access control outside this class
    String speed;
    String color;

    //Constructor function
    public Car(String args1, String args2, String args3){
        this.name = args1; //whatever object we are talking about here, set its name as args1
        this.speed = args2;
        this.color = args3;
    }

    //Setter function
    void setName(String newName){
        this.name = newName; //We are setting the neew name here
    }

    //Getter function i.e why it is public
    public String getName(){
        return name; //returning the name as a string
    }

    void drive(){
        System.out.println( name + " is driving");
    }
}
```

---

### ✔️ Test.java

```java
package com.rcs.javalearning.datatypes;

public class Test {
    public static void main(String[] args){
        Car mycar1 = new Car("Bugatti", "100kmp", "Black");
        
        //If i write as below, then anyone is editing this car name from Bugatti to Tesla, which is wrong
            //mycar1.name = "Tesla"; 
        // So that is why, we will make the "name" as private in parent class and will user setter function
        
        //first get name using getter function written in parent class Car.java->
        String carName = mycar1.getName();
        System.out.println("Original car name -" + carName);
        
        //now calling setter function to set the name ->
        mycar1.setName("Tesla - Electric");
        
        mycar1.drive();
    }
}

```
---
## Output-
Original car name -Bugatti </br>
Tesla - Electric is driving

<p>(As you can see, we are able to change the name of the car from Bugatti to Tesla, but we are doing it through setter function, which is a controlled way to change the data. We can also add validation inside setter function to prevent invalid data.)</p>
---

## 🔐 What Changed?

| Before ❌         | After ✅                |
| ---------------- | ---------------------- |
| Public variables | Private variables      |
| Direct access    | Controlled via methods |
| No validation    | Validation possible    |

---

## 🎯 Why Encapsulation is Good?

* ✔ Protects data from misuse
* ✔ Allows validation before updating
* ✔ Makes code secure and maintainable
* ✔ Improves control over data

---

## 👶 Simple Understanding

* Data = 🔒 Locked
* Methods = 🔑 Keys

👉 Only allowed actions can access data

---

## 💬 Interview Definition

> “Encapsulation is the process of wrapping data and methods into a single unit and restricting direct access to the data using access modifiers, typically achieved using private variables and public getter/setter methods.”

<a id="-java-oop---inheritance-2nd-pillar-🚀"></a>
# ☕ Java OOP — Inheritance (2nd Pillar) 🚀

---

## 📌 What is Inheritance?

**Inheritance** means:

> **One class can use (inherit) the properties and methods of another class.**

---

## 👶 Simple Definition

👉 **“Child class uses features of parent class.”**

---

## 🧠 Why Do We Need Inheritance?

Without inheritance:

* You repeat same code again and again ❌
* Hard to maintain ❌

With inheritance:

* Reuse code ✅
* Clean structure ✅
* Easy to extend functionality ✅

---

## 👶 Real-Life Understanding

Think:

* Parent → Animal 🐾
* Child → Dog 🐶

👉 Every dog **is an animal**

So:

* Dog can **eat** (from Animal)
* Dog can also **bark** (its own behavior)

---

## ⚙️ Example Without Inheritance (Problem)

```java
class Dog {
    void eat(){
        System.out.println("Dog is eating");
    }
}

class Cat {
    void eat(){
        System.out.println("Cat is eating");
    }
}
```

❌ Duplicate code (`eat()` repeated)

---

## ✅ Using Inheritance

### ✔️ Parent Class (Animal.java)

```java
package com.rcs.javalearning.datatypes;

public class Animal {
    public void eat(String Animal){
        System.out.println(Animal + " is eating");
    }
}
```

### ✔️ Child Class (Dog.java)

```java
package com.rcs.javalearning.datatypes;

public class Dog extends Animal {
    public void bark(){
        System.out.println("Dog is barking");
    }
}
```

### ✔️ Main Class (Test.java)

```java
package com.rcs.javalearning.datatypes;

public class Test {
    public static void main(String[] args){
        Dog mydog1 = new Dog();
        mydog1.eat("Dog");
        mydog1.bark();
    }
}
```

---

Below is the output:
* Dog is eating
* Dog is barking

---

## 🔍 What Happened?

* `Dog` **extends** `Animal`  
* So Dog gets:
  * `eat()` ✅ (from Animal)
  * `bark()` ✅ (its own)


---

## 🧠 Key Concept

```java
class Dog extends Animal
```

👉 Means:

> Dog is a type of Animal

---

## 🎯 Benefits of Inheritance

* ✔ Code reuse
* ✔ Less duplication
* ✔ Easy to maintain
* ✔ Better structure

---

## 👶 Simple Analogy

* Animal = Parent 👨
* Dog = Child 👦

👉 Child automatically gets basic features and can add its own skills.

---

## 💬 Interview Definition

> “Inheritance is an OOP concept where one class acquires the properties and methods of another class using the extends keyword, enabling code reuse and hierarchical relationships.”

---

## 🚀 Final Summary

👉 Write once, reuse everywhere 👍





