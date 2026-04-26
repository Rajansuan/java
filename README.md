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
    - [Multilevel Inheritance](#multilevel-inheritance) 🔁
    - [Hierarchical Inheritance](#hierarchical-inheritance) 🌳
    - [Why Java Does NOT Support Multiple Inheritance (Classes)](#why-java-does-not-support-multiple-inheritance) ❌
  - [Polymorphism (3rd Pillar)](#-java-oop---polymorphism-3rd-pillar-🧠) 🧠
    - [Compile-Time Polymorphism](#compile-time-polymorphism) ⏱️
    - [Runtime Polymorphism](#runtime-polymorphism) ⏳
  - [Abstraction (4th Pillar)](#-java-oop---abstraction-4th-pillar) 🎭
    - [Interface](#interface) 🧩
    - [Abstract Class vs Interface](#abstract-vs-interface) ⚔️
    - [Static & Default Methods in Interface](#-java-oop---static-default-methods-in-interface) ⚡
- [Access Modifiers](#access-modifiers) 🔐
- [Multithreading](#multithreading) 🧵
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
<a id="single-level-inheritance"></a>
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

## Understanding Object Data & Variables

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
    public void setName(String newName){
        this.name = newName; //We are setting the neew name here
    }

    //Getter function i.e why it is public
    public String getName(){
        return name; //returning the name as a string
    }

    public void drive(){
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

## ✅ Using Inheritance -

# This is a -> Single Level Inheritance
One class (Dog) inherits from another class (Animal)

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
👉 Write once, reuse everywhere 👍


<a id="multilevel-inheritance"></a>
<a id="multilevel"></a>
# ☕ Java OOP — Multilevel Inheritance

---

## 📌 What is Multilevel Inheritance?

**Multilevel Inheritance** means:

> A class inherits from a parent class, and that parent class itself inherits from another class.

---

## 👶 Simple Definition

👉 **“Child → Parent → Grandparent chain”**

---

## 🧠 Real-Life Understanding

Think of a family:

* Grandparent 👴
* Parent 👨
* Child 👦

👉 Child gets:

* Features from Parent
* Features from Grandparent

---

## ⚙️ Structure

```java
Grandparent → Parent → Child
```

---

## ✅ Example (Animal → Dog → Puppy)

---

### ✔️ Grandparent Class (Animal.java)

```java
package com.rcs.javalearning.datatypes;

public class Animal {
  public void eat(String name){
    System.out.println(name + " is eating");
  }
}
```

---

### ✔️ Parent Class (Dog.java)

```java
package com.rcs.javalearning.datatypes;

public class Dog extends Animal {
  public void bark(){
    System.out.println("Dog is barking");
  }
}
```

---

### ✔️ Child Class (Puppy.java)

```java
package com.rcs.javalearning.datatypes;

public class Puppy extends Dog {
  public void weep(){
    System.out.println("Puppy is weeping");
  }
}
```

---

### ✔️ Main Class (Test.java)

```java
package com.rcs.javalearning.datatypes;

public class Test {
  public static void main(String[] args){

    Puppy mypuppy = new Puppy();

    mypuppy.eat("Puppy");  // now uses parameter
    mypuppy.bark();        
    mypuppy.weep();        
  }
}
```

---

## 🔍 Output

```
Puppy is eating
Dog is barking
Puppy is weeping
```

---

## 🔎 What Happened?

* `Puppy` extends `Dog`
* `Dog` extends `Animal`

👉 So Puppy gets:

* `eat(String name)` ✅ (from Animal)
* `bark()` ✅ (from Dog)
* `weep()` ✅ (its own)

---

## 🧠 Key Concept

```java
class Puppy extends Dog
class Dog extends Animal
```

👉 Means:

> Puppy is a Dog, and Dog is an Animal

---

## 🎯 Benefits of Multilevel Inheritance

* ✔ Code reuse at multiple levels
* ✔ Logical hierarchy
* ✔ Easy to extend

---

## 👶 Simple Analogy

* Animal = Grandparent 👴
* Dog = Parent 👨
* Puppy = Child 👦

👉 Child gets everything from both

---

## 💬 Interview Line

> “Multilevel inheritance is a type of inheritance where a class inherits from another class, which itself inherits from a third class, forming a chain of inheritance.”

---


<a id="hierarchical-inheritance"></a>
<a id="hierarchical"></a>
# ☕ Java OOP — Hierarchical Inheritance

---

## 📌 What is Hierarchical Inheritance?

**Hierarchical Inheritance** means:

> **Multiple child classes inherit from the same parent class**

---

## 👶 Simple Definition

👉 **“One Parent → Many Children”**

---

## 🧠 Real-Life Understanding

Think:

* Animal 🐾 (Parent)
* Dog 🐶 (Child)
* Cat 🐱 (Child)

👉 Both Dog and Cat:

* Can **eat** (common behavior from Animal)
* Have their **own behaviors**

---

## ⚙️ Structure

```java id="l3k9pt"
    Animal
    /    \
   Dog     Cat
```

---

## ✅ Example

---

### ✔️ Parent Class (Animal.java)

```java id="c2q8xv"
package com.rcs.javalearning.datatypes;

public class Animal {
  public void eat(String name){
    System.out.println(name + " is eating");
  }
}
```

---

### ✔️ Child Class 1 (Dog.java)

```java id="v7n2dw"
package com.rcs.javalearning.datatypes;

public class Dog extends Animal {
  public void bark(String name){
    System.out.println(name + " is barking");
  }
}
```

---

### ✔️ Child Class 2 (Cat.java)

```java id="r4k1mz"
package com.rcs.javalearning.datatypes;

public class Cat extends Animal {
  public void meow(String name){
    System.out.println(name + " is meowing");
  }
}
```

---

### ✔️ Main Class (Test.java)

```java id="k5p9yj"
package com.rcs.javalearning.datatypes;

public class Test {
  public static void main(String[] args){

    Dog dog = new Dog();
    dog.eat("Dog");
    dog.bark("Dog");

    System.out.println();

    Cat cat = new Cat();
    cat.eat("Cat");
    cat.meow("Cat");
  }
}
```

---

## 🔍 Output

```id="q8f2zx"
Dog is eating
Dog is barking

Cat is eating
Cat is meowing
```

---

## 🔎 What Happened?

* `Dog` extends `Animal`
* `Cat` extends `Animal`

👉 Both reuse:

* `eat()` from Animal

👉 And have their own:

* `bark()`
* `meow()`

---

## 🧠 Key Concept

```java id="m1x7dp"
class Dog extends Animal
class Cat extends Animal
```

👉 Means:

> Multiple classes share same parent

---

## 🎯 Benefits

* ✔ Code reuse
* ✔ Avoid duplication
* ✔ Easy to manage common behavior

---

## 👶 Simple Analogy

* Parent = Animal 👨
* Children = Dog 🐶, Cat 🐱

👉 Both children inherit common traits

---

## 💬 Interview Line

> “Hierarchical inheritance is a type of inheritance where multiple child classes inherit from a single parent class, allowing reuse of common functionality.”

---

<a id="why-java-does-not-support-multiple-inheritance"></a>
<a id="multiple-inheritance"></a>
<a id="multiple-inheritance-classes"></a>
# ☕ Java OOP — Why Java Does NOT Support Multiple Inheritance (Classes)

---

## 📌 What is Multiple Inheritance?

**Multiple Inheritance** means:

> A class tries to inherit from **more than one parent class**

---

## 🧠 Example Scenario

We have different classes:

* 📷 `Camera` → takes photos
* 🎵 `MusicPlayer` → plays music
* 📞 `Phone` → makes calls

Now we want:

👉 A `SmartPhone` class that has **all features**

---

## ❌ What We Want to Do (Not Allowed in Java)

```java
class SmartPhone extends Camera, MusicPlayer, Phone {
}
```

👉 ❌ Java does NOT allow this

---

## 🤯 Why Java Does NOT Support This?

### ⚠️ Problem: Method Conflict (Diamond Problem)

Assume all classes have same method:

```java
class Camera {
  void turnOn(){
    System.out.println("Camera turning on");
  }
}

class MusicPlayer {
  void turnOn(){
    System.out.println("Music Player turning on");
  }
}

class Phone {
  void turnOn(){
    System.out.println("Phone turning on");
  }
}
```

---

## ❓ Now Problem

If Java allowed:

```java
class SmartPhone extends Camera, MusicPlayer, Phone
```

Then:

```java
SmartPhone s = new SmartPhone();
s.turnOn();
```

👉 ❓ Which `turnOn()` should run?

* Camera’s? 📷
* MusicPlayer’s? 🎵
* Phone’s? 📞

👉 Java gets **confused**

---

## 🚨 This is called

> **Ambiguity Problem (Diamond Problem)**

---

## 🧠 Key Reason

👉 Java avoids multiple inheritance in classes to:

* ❌ Prevent confusion
* ❌ Avoid ambiguity
* ❌ Keep code simple and predictable

---

## ✅ What Java Allows

👉 Only:

```java
class SmartPhone extends Phone
```

👉 One parent only

---

## ⚡ Important Note

👉 This problem **can be solved using Interfaces**

✔ Interfaces allow multiple inheritance
✔ No ambiguity (we will study below)

---

## 💬 Interview Line

> “Java does not support multiple inheritance using classes to avoid ambiguity and method conflicts (diamond problem), ensuring code simplicity and clarity. This limitation is overcome using interfaces.”

<a id="-java-oop---polymorphism-3rd-pillar-🧠"></a>
<a id="polymorphism"></a>
<a id="polymorphism-3rd-pillar"></a>
# ☕ Java OOP — Polymorphism (3rd Pillar)

---

## 📌 What is Polymorphism?

* **Poly** = Many
* **Morph** = Forms

👉 **Polymorphism = Many Forms**

---

## 👶 Simple Definition

> **Polymorphism allows methods to perform different tasks based on how they are called.**

---

## ⚙️ Types of Polymorphism

1. **Compile-Time Polymorphism** → Method Overloading
2. **Runtime Polymorphism** → Method Overriding 

---
<a id="compile-time-polymorphism"></a>
# 🧠 Compile-Time Polymorphism

👉 Decided at **compile time**
👉 Based on **method parameters**

---

## 👶 Simple Example (Calculator)

```java
class Calculator {

  // 2 parameters
  int add(int a, int b){
    return a + b;
  }

  // 3 parameters
  int add(int a, int b, int c){
    return a + b + c;
  }
}
```

---

## ✔️ Main Class

```java
public class Test {
  public static void main(String[] args){

    Calculator calc = new Calculator();

    System.out.println(calc.add(2, 3));        // calls 2 param method
    System.out.println(calc.add(2, 3, 4));     // calls 3 param method
  }
}
```

---

## 🔍 Output

```
5
9
```

---

## 🧠 How Compiler Decides?

👉 Based on:

* Number of parameters
* Type of parameters
* Order of parameters

---

# 📌 Method Overloading Definition

> **Method Overloading is a feature where multiple methods have the same name but different parameters (number, type, or order).**

---

# ⚙️ Types of Overloading

---

## 1️⃣ Different Number of Parameters

```java
int add(int a, int b)
int add(int a, int b, int c)
```

---

## 2️⃣ Different Type of Parameters

```java
int add(int a, int b){
  return a + b;
}

double add(double a, double b){
  return a + b;
}
```

---

## 3️⃣ Different Order of Parameters

```java
void display(int a, String b){
  System.out.println("int then string");
}

void display(String b, int a){
  System.out.println("string then int");
}
```

---

## ✔️ Main Example

```java
public class Test {
  public static void main(String[] args){

    Demo d = new Demo();

    d.display(10, "Hello");   // int, String
    d.display("Hello", 10);   // String, int
  }
}
```

---

# ❌ Important Rule

👉 You **CANNOT overload** only by changing return type

```java
// ❌ INVALID
int add(int a, int b)
double add(int a, int b)
```

👉 Compiler will give error

---

# 🎯 Final Understanding

* Same method name ✅
* Different parameters ✅
* Compiler decides which method to call

---

# 👶 Simple Analogy

👉 Same person, different roles:

* Add 2 numbers → simple addition
* Add 3 numbers → extended addition

👉 Same function name, different behavior

---

# 💬 Interview Line

> “Compile-time polymorphism is achieved using method overloading, where multiple methods have the same name but differ in parameters, and the compiler determines which method to invoke.”

<a id="runtime-polymorphism"></a>
# 🧠 Runtime Polymorphism

# ☕ Java OOP — Runtime Polymorphism (Method Overriding)

---

## 📌 Definition

> **Runtime polymorphism is achieved through method overriding, where a subclass provides a specific implementation of a method already defined in its parent class. The method to be executed is decided at runtime based on the object.**

---

## 👶 Simple Understanding

👉 Same method name
👉 Different behavior
👉 Based on **object type at runtime**

---

# ⚙️ Example

---

## ✔️ Parent Class (Animal.java)

```java
package com.rcs.javalearning.oops;

public class Animal {
  public void sound(){
    System.out.println("Animal makes a sound");
  }
}
```

---

## ✔️ Child Class (Dog.java)

```java
package com.rcs.javalearning.oops;

public class Dog extends Animal {
  @Override
  public void sound(){
    System.out.println("Dog is barking");
  }
}
```

---

## ✔️ Child Class (Cat.java)

```java
package com.rcs.javalearning.oops;

public class Cat extends Animal {
  @Override
  public void sound(){
    System.out.println("Cat meows");
  }
}
```

---

## ✔️ Main Class (Test.java)

```java
package com.rcs.javalearning.oops;

public class Test {
  public static void main(String[] args){

    Animal mypet1 = new Dog();
    Animal mypet2 = new Cat();

    mypet1.sound();
    mypet2.sound();
  }
}
```

---

# 🤯 Important Question

## ❓ Why can we write:

```java
Animal mypet1 = new Dog();
```

---

## 🧠 Answer

👉 Because:

> **Dog IS-A Animal**

✔ Dog extends Animal
✔ So Dog can be treated as Animal

---

## 👶 Simple Analogy

👉 Animal = Parent
👉 Dog = Child

You can say:

👉 “This is an Animal” (correct)
👉 Even if it is actually a Dog

---

## 🔑 Key Concept

```java
Animal mypet1 = new Dog();
```

* Reference type = Animal
* Object type = Dog

👉 Method call depends on **object type (Dog)**

---

# 🔍 Output

```text
Dog is barking
Cat meows
```

---

# 🤯 What Happened?

| Variable | Object | Method Called |
| -------- | ------ | ------------- |
| mypet1   | Dog    | Dog’s sound() |
| mypet2   | Cat    | Cat’s sound() |

---

## 🧠 Key Concept

> Method is resolved at **runtime**, not compile time

---

# 🎯 Why It is Called Runtime Polymorphism?

👉 Because Java decides:

> Which method to run → at runtime based on object

---

# 💬 Interview Line

> “Runtime polymorphism is achieved using method overriding, where the method call is resolved at runtime based on the object type rather than the reference type.”

---

# 🚀 Final Summary

* Same method → `sound()`
* Different implementations → Dog, Cat
* Decision happens → runtime
* Based on → object type 👍

<a id="-java-oop---abstraction-4th-pillar"></a>
<a id="abstraction"></a>
<a id="abstraction-4th-pillar"></a>
# ☕ Java OOP — Abstraction (4th Pillar)

---

## 📌 What is Abstraction?

> **Abstraction focuses on showing only essential details while hiding the implementation.**

---

## 👶 Simple Definition

👉 **“Show what to do, hide how it is done.”**

---

## 🧠 Real-Life Example

Think of a **car gear system 🚗**

* You just change the gear
* You don’t know:

  * How engine works
  * How gears shift internally

👉 You use the feature without knowing internal logic

---

## ⚙️ How Java Achieves Abstraction?

👉 Using:

* **Abstract Classes**
* **Interfaces** 

---

# 🧱 Abstract Class

---

## 📌 Key Points

* Declared using `abstract` keyword
* Can have:

  * Abstract methods (no body)
  * Concrete methods (with body)
* ❌ Cannot create object directly
* ✔ Used as blueprint for subclasses

---

# ⚙️ Example

---

## ✔️ Abstract Parent Class (Animal.java)

```java id="a1x7bz"
package com.rcs.javalearning.oops;

public abstract class Animal {

  // 🔸 Abstract method (no body)
  public abstract void sound();

  // 🔸 Concrete method (with body)
  public void eat(){
    System.out.println("Animal is eating");
  }
}
```

---

## ✔️ Child Class (Dog.java)

```java id="9h3t6m"
package com.rcs.javalearning.oops;

public class Dog extends Animal {

  // 🔹 Must override abstract method
  @Override
  public void sound(){
    System.out.println("Dog is barking");
  }
}
```

---

## ✔️ Main Class (Test.java)

```java id="t8z2kc"
package com.rcs.javalearning.oops;

public class Test {
  public static void main(String[] args){

    Animal mypet = new Dog(); // cannot create Animal directly

    mypet.sound(); // abstract method implemented by Dog
    mypet.eat();   // concrete method from Animal
  }
}
```

---

## 🔍 Output

```text id="m7f0dq"
Dog is barking
Animal is eating
```

---

# 🤯 Important Points

## ❓ Why we cannot do this?

```java id="v1z3os"
Animal a = new Animal(); // ❌ ERROR
```

👉 Because:

* Abstract class is **incomplete**
* It has abstract methods (no body)

---

## 🧠 Key Concept

| Type            | Meaning                      |
| --------------- | ---------------------------- |
| Abstract Method | No body, must be implemented |
| Concrete Method | Has body, ready to use       |

---

# 🎯 What Happened?

* `Animal` defines structure
* `Dog` provides implementation
* Object decides behavior

---

# ☕ Java OOP — Abstraction (Real-Life Example)

---

## 📌 What is Abstraction?

> **Abstraction focuses on showing only essential details while hiding the implementation.**

---

## 👶 Simple Definition

👉 **“Show what to do, hide how it is done.”**

---

## 🧠 Real-Life Example — Payment System 💳

Think of apps like:

* Google Pay
* Paytm

---

### 👉 What YOU Do

* Click **Pay ₹500**
* Choose payment method:

  * UPI
  * Credit Card
  * Net Banking

👉 Payment done ✅

---

### 🤯 What YOU DON’T See

* Bank communication
* Authentication
* Security checks
* Transaction processing

👉 All hidden 🔒

---

## 🎯 This is Abstraction

> You use a simple interface (`pay`)
> System handles complex logic internally

---

# ⚙️ Java Code Example

---

## ✔️ Abstract Class (Payment.java)

```java id="9e4k2n"
abstract class Payment {
    abstract void pay(int amount);
}
```

---

## ✔️ UPI Implementation (UPI.java)

```java id="n1x9q3"
class UPI extends Payment {
    void pay(int amount){
        System.out.println("Paid " + amount + " using UPI");
    }
}
```

---

## ✔️ Credit Card Implementation (CreditCard.java)

```java id="4f8j2s"
class CreditCard extends Payment {
    void pay(int amount){
        System.out.println("Paid " + amount + " using Credit Card");
    }
}
```

---

## ✔️ Main Class (Test.java)

```java id="z7k3m1"
public class Test {
    public static void main(String[] args){

        Payment p1 = new UPI();
        Payment p2 = new CreditCard();

        p1.pay(500);
        p2.pay(1000);
    }
}
```

---

## 🔍 Output

```text id="p0x2d9"
Paid 500 using UPI
Paid 1000 using Credit Card
```

---

## 🤯 What Happened?

* You call `pay()`
* You don’t care how payment happens
* Different classes handle their own logic

---

## 🧠 Why This is Powerful?

* ✔ Hides complexity
* ✔ Easy to use
* ✔ Flexible (add new payment methods easily)
* ✔ Clean and scalable code

---

## 👶 Simple Analogy

Abstraction = Food delivery app 🍔

* You order food
* You don’t cook
* You don’t deliver

👉 Everything happens behind the scenes

---

## 💬 Interview Line

> “A real-life example of abstraction is a payment system where users perform transactions without knowing the internal implementation, similar to abstract classes defining behavior without exposing details.”

---

## 🚀 Final Summary

* Abstract class = common interface
* Subclasses = implementation
* User = interacts without knowing internal logic

👉 **Abstraction = Simplicity + Hidden Complexity 👍**

<a id="interface"></a>

# ☕ Java OOP — Interface (Abstraction + Multiple Inheritance)

---

## 📌 What is an Interface?

* **Class → Blueprint for Object**
* **Interface → Blueprint for Class**

---

## 👶 Simple Definition

> **An interface defines WHAT a class should do, not HOW it does it.**

---

## 🧠 Key Points

* Declared using `interface` keyword
* Methods are **abstract by default**
* Cannot create object of interface ❌
* Class uses `implements` keyword
* Supports **multiple inheritance** ✅

---

## 🎯 Why Interface?

👉 Achieves:

* ✔ Abstraction (hide implementation)
* ✔ Multiple inheritance (a class can implement multiple interfaces)

---

# ⚙️ Real Example — Smartphone 📱

We want a `SmartPhone` that can:

* Take photos 📷
* Play music 🎵
* Make calls 📞

---

## ❌ Problem with Classes

```java
class SmartPhone extends Camera, MusicPlayer, Phone // ❌ NOT ALLOWED
```

👉 Java does NOT allow multiple inheritance with classes

---

## ✅ Solution: Use Interfaces

---

## ✔️ Camera Interface

```java id="c1"
interface Camera {
  void clickPhoto();
}
```

---

## ✔️ MusicPlayer Interface

```java id="c2"
interface MusicPlayer {
  void playMusic();
}
```

---

## ✔️ Phone Interface

```java id="c3"
interface Phone {
  void makeCall();
}
```

---

## ✔️ SmartPhone Class

```java id="c4"
class SmartPhone implements Camera, MusicPlayer, Phone {

  public void clickPhoto(){
    System.out.println("Photo clicked");
  }

  public void playMusic(){
    System.out.println("Music playing");
  }

  public void makeCall(){
    System.out.println("Calling...");
  }
}
```

---

## ✔️ Main Class

```java id="c5"
public class Test {
  public static void main(String[] args){

    SmartPhone sp = new SmartPhone();

    sp.clickPhoto();
    sp.playMusic();
    sp.makeCall();
  }
}
```

---

## 🔍 Output

```text id="c6"
Photo clicked
Music playing
Calling...
```

---

## 🤯 What Happened?

* `SmartPhone` implements:

  * Camera
  * MusicPlayer
  * Phone

👉 So it gets **all functionalities**

---

## 🧠 Key Concept

```java
class SmartPhone implements Camera, MusicPlayer, Phone
```

👉 Means:

> One class can follow rules of multiple interfaces

---

## 🎯 Benefits of Interface

* ✔ Supports multiple inheritance
* ✔ Enforces structure
* ✔ Loose coupling (flexible code)
* ✔ Easy to extend

---

## 👶 Simple Analogy

Interface = Rules 📜

* Camera → must click
* Music → must play
* Phone → must call

👉 SmartPhone follows all rules

---

## 💬 Interview Line

> “An interface is a blueprint for a class that defines abstract methods, allowing a class to implement multiple behaviors and achieve abstraction and multiple inheritance.”

---

## 🚀 Final Summary

* Interface = blueprint for class
* Achieves abstraction
* Allows multiple inheritance
* Class implements multiple interfaces 👍


<a id="-java-oop---abstract-vs-interface"></a>
<a id="abstract-vs-interface"></a>
# ☕ Java OOP — Abstract Class vs Interface
## 🧠 Goal

👉 Understand **WHEN to use Abstract Class**
👉 Understand **WHEN to use Interface**

---

# 🧱 Abstract Class — Real-Life Example

## 📌 Scenario: Vehicle System 🚗

All vehicles have:

* Engine
* Fuel
* Common behavior like `start()`

But:

* Car 🚗 starts differently
* Bike 🏍️ starts differently

---

## ✔️ Why Abstract Class?

👉 Because:

* Some logic is **common**
* Some logic is **different**

---

## ✔️ Example

```java id="veh1"
abstract class Vehicle {

  void fuelType(){
    System.out.println("Vehicle uses fuel");
  }

  abstract void start(); // different for each vehicle
}
```

---

```java id="veh2"
class Car extends Vehicle {
  void start(){
    System.out.println("Car starts with key");
  }
}
```

---

```java id="veh3"
class Bike extends Vehicle {
  void start(){
    System.out.println("Bike starts with kick");
  }
}
```

---

## 🎯 Why Abstract Here?

* ✔ Common code reused (`fuelType`)
* ✔ Specific behavior forced (`start`)
* ✔ Logical hierarchy (Vehicle → Car/Bike)

---

# 📜 Interface — Real-Life Example

## 📌 Scenario: SmartPhone Features 📱

A smartphone can:

* Take photos 📷
* Play music 🎵
* Make calls 📞

👉 These are **independent features**

---

## ✔️ Why Interface?

👉 Because:

* No common base logic
* Only **capabilities (features)**
* Multiple features needed

---

## ✔️ Example

```java id="int1"
package com.rcs.javalearning.datatypes.interfaces;

public interface Calling{
    public void callingPhone(String args);
}
```

Simarily, we can create `Camera` and `MusicPlayer` interfaces with their own methods as below.

```java
package com.rcs.javalearning.datatypes.interfaces;

public interface Camera{
    public void clickPhoto(String args);
}
```

```java
package com.rcs.javalearning.datatypes.interfaces;

public interface MusicPlayer{
    public void playMusic(String args);
}
```

---

```java id="int2"
package com.rcs.javalearning.datatypes;
import com.rcs.javalearning.datatypes.interfaces.Calling;
import com.rcs.javalearning.datatypes.interfaces.Camera;
import com.rcs.javalearning.datatypes.interfaces.MusicPlayer;

public class SmartPhone implements Camera, Calling, MusicPlayer {

    @Override
    public void clickPhoto(String args) {
        System.out.println(args + " is clicking photo");
    }

    @Override
    public void callingPhone(String args){
        System.out.println(args + " is calling");
    }

    @Override
    public void playMusic(String args){
        System.out.println(args + " is playing music");
    }
}
```

---

## 🎯 Why Interface Here?

* ✔ Multiple features
* ✔ No shared logic
* ✔ Flexible design

---

# ⚔️ Final Comparison

| Use Case                   | Abstract Class | Interface |
| -------------------------- | -------------- | --------- |
| Common base + shared logic | ✅              | ❌         |
| Only define capabilities   | ❌              | ✅         |
| Single inheritance         | ✅              | ❌         |
| Multiple features          | ❌              | ✅         |

---

# 👶 Simple Analogy

* Abstract Class = Family 👨‍👩‍👦
* Interface = Skills 🎯

---

# 🧠 Final Understanding

👉 Use **Abstract Class** when:

* You have **common base logic**
* You want **inheritance hierarchy**

---

👉 Use **Interface** when:

* You need **multiple features**
* You want **flexibility**

---

# 💬 Interview Answer

> “Abstract classes are used when classes share common state and behavior, while interfaces are used to define capabilities that can be implemented by multiple unrelated classes.”

---

# 🚀 Final Summary

* Abstract = “What you ARE”
* Interface = “What you CAN DO”

👉 **Abstract = Structure | Interface = Capability 👍**

<a id="-java-oop---static-default-methods-in-interface"></a>
# ☕ Java OOP — Static & Default Methods in Interface

---

## 📌 Why These Exist?

Earlier in Java, interfaces could only have **abstract methods**.

But, Now they can also have:

* ✔ **Default methods** (with body)
* ✔ **Static methods** (with body)

👉 This makes interfaces more powerful and flexible

---

# ⚙️ 1. Default Methods in Interface

---

## 🧠 What is Default Method?

> A **default method** is a method inside an interface that has a body and can be used directly by implementing classes.

---

## 👶 Simple Definition

👉 “Interface gives a **default behavior**, but class can override it”

---

## 🧠 Real-Life Example — Smart Devices 📱

All devices can:

* Turn ON 🔌

👉 Default behavior is same, but can be customized

---

## ✔️ Example

```java
interface Device {
  default void turnOn(){
    System.out.println("Device is turning ON");
  }
}
```

---

```java
class Phone implements Device {
  // using default method
}
```

---

```java
public class Test {
  public static void main(String[] args){
    Phone p = new Phone();
    p.turnOn(); // default method used
  }
}
```

---

## 🔍 Output

```
Device is turning ON
```

---

## 🤯 Override Default Method

```java
class Phone implements Device {
  @Override
  public void turnOn(){
    System.out.println("Phone is turning ON");
  }
}
```

---

# ⚙️ 2. Static Methods in Interface

---

## 🧠 What is Static Method?

> A **static method** belongs to the interface itself and cannot be overridden.

---

## 👶 Simple Definition

👉 “Utility method inside interface”

---

## 🧠 Real-Life Example — Payment System 💳

You want a **common validation method**

👉 Same for all → no need to override

---

## ✔️ Example

```java
interface Payment {

  static void validate(){
    System.out.println("Validating payment...");
  }
}
```

---

```java
public class Test {
  public static void main(String[] args){

    Payment.validate(); // called using interface name
  }
}
```

---

## 🔍 Output

```
Validating payment...
```

---

# ⚠️ Important Rule

```java
Payment.validate(); // ✅ correct
```

```java
p.validate(); // ❌ wrong
```

👉 Static methods are NOT called using object

---

# ⚔️ Difference: Default vs Static

| Feature      | Default Method   | Static Method  |
| ------------ | ---------------- | -------------- |
| Belongs to   | Object           | Interface      |
| Can override | ✅ Yes            | ❌ No           |
| Called using | Object           | Interface name |
| Purpose      | Default behavior | Utility/helper |

---

# 👶 Simple Analogy

* Default method = “Standard feature” 📱
* Static method = “Tool/utility” 🔧

---

# 🎯 When to Use

👉 Use **Default**:

* When most classes share behavior
* But some may change it

👉 Use **Static**:

* For common utility logic
* No need to override

---

# 💬 Interview Line

> “Default methods in interfaces provide a method implementation that can be overridden by implementing classes, while static methods belong to the interface and are called using the interface name and cannot be overridden.”

---

# 🚀 Final Summary

* Default → customizable behavior
* Static → fixed utility method
* Both improve interface flexibility 👍


---
<a id="access-modifiers"></a>
# ☕ Java OOP — Access Modifiers

---

## 📌 What are Access Modifiers?

> **Access Modifiers control the visibility (who can access) of classes, variables, and methods.**

---

## 🧠 Types of Access Modifiers

1. **public**
2. **private**
3. **protected**
4. **default (no keyword)**

---

# ⚙️ 1. public

👉 Accessible **from anywhere**

```java
public class Car {
  public String name;
}
```

✔ Any class from any package can use it

---

# ⚙️ 2. private

👉 Accessible **only within the same class**

```java
class Car {
  private String name;
}
```

✔ Cannot be accessed outside the class

---

# ⚙️ 3. protected

👉 Accessible:

* Within same package
* In subclasses (even in different package)

```java
class Car {
  protected String name;
}
```

---

# ⚙️ 4. default (no modifier)

👉 Accessible **only within same package**

```java
class Car {
  String name; // default
}
```

---

# 📊 Access Modifier Table

| Modifier  | Same Class | Same Package | Subclass (Other Package) | Other Package |
| --------- | ---------- | ------------ | ------------------------ | ------------- |
| public    | ✅          | ✅            | ✅                        | ✅             |
| protected | ✅          | ✅            | ✅                        | ❌             |
| default   | ✅          | ✅            | ❌                        | ❌             |
| private   | ✅          | ❌            | ❌                        | ❌             |
---

# 💬 Interview Line

> “Access modifiers in Java define the scope of visibility of variables and methods. Private restricts access within the class, while protected allows access within the package and to subclasses.”

---

# 🚀 Final Summary

* public → open for all 🌍
* private → only inside class 🔒
* protected → family + subclass 🛡️
* default → same package only 📦

👉 **Access Modifiers = Control Visibility 👍**

<hr>

<a id="multithreading"></a>

# ☕ Java — Multithreading (Basics)

---

## 🧠 CPU (Central Processing Unit)

> **CPU is the brain of the computer** 🧠

* Executes instructions from programs
* Performs calculations, input/output operations

---

## ⚙️ What is a Core?

> **Core = Individual processing unit inside CPU**

* Modern CPUs have multiple cores
* Each core can run tasks independently

👉 Example:

* **Quad-core CPU** → 4 tasks at same time

---

## 📌 What is a Program?

> **Program = Set of instructions written in a programming language**

👉 Example:

* Microsoft Word → used to create/edit documents

---

## 📌 What is a Process?

> **Process = Running instance of a program**

👉 When you open MS Word:

* OS creates a **process**

---

## 📌 What is a Thread?

> **Thread = Smallest unit of execution inside a process**

* A process can have multiple threads
* Threads share same memory/resources
* Can run independently

---

## 👶 Example

👉 Google Chrome 🌐

* Each tab = separate thread
* All inside one process

---

# ⚙️ Multitasking vs Multithreading

---

## 🧠 Multitasking (OS Level)

> Running multiple processes simultaneously

👉 Example:

* Chrome + Word + Music Player running together

---

## 🧠 Multithreading (Within Process)

> Running multiple threads inside one process

👉 Example:

* Chrome → multiple tabs

---

## ⚔️ Difference Table

| Feature | Multitasking  | Multithreading |
| ------- | ------------- | -------------- |
| Level   | OS level      | Process level  |
| Unit    | Process       | Thread         |
| Example | Chrome + Word | Tabs in Chrome |

---

# ⚙️ What is Multithreading?

> **Multithreading = Running multiple threads within a single process concurrently**

---

## 🎯 Benefits

* ✔ Better performance
* ✔ Faster execution
* ✔ Improved responsiveness

---

# ☕ Multithreading in Java

---

## 📌 Key Point

👉 Java has built-in support for multithreading

👉 Available in:

```java id="p7x8k1"
java.lang package
```

---

## 🧠 Single-Core Environment

* Only one core available
* Threads don’t run truly parallel
* JVM + OS switch between threads

👉 This is called:

> **Context Switching / Time Slicing**

---

## ⏱️ Time Slicing

> CPU gives small time to each thread

👉 Creates illusion of parallel execution

---

## 🧠 Multi-Core Environment

* Multiple cores available
* Threads can run **truly parallel**

👉 JVM distributes threads across cores

---

# 🔥 Key Understanding

| Environment | Execution              |
| ----------- | ---------------------- |
| Single Core | Concurrency (illusion) |
| Multi Core  | True Parallelism       |

---

# 👶 Simple Analogy

👉 Chef 🍳 in kitchen:

* Single chef → cooks dishes one by one quickly (time slicing)
* Multiple chefs → cook simultaneously (parallelism)

---

# 💬 Interview Line

> “Multithreading in Java allows multiple threads to execute concurrently within a process, improving performance and responsiveness. In single-core systems it uses time-slicing, while in multi-core systems it achieves true parallel execution.”

---

# 🚀 Quick Summary

* Program → Instructions
* Process → Running program
* Thread → Small execution unit
* Multitasking → Multiple processes
* Multithreading → Multiple threads

👉 **Multithreading = Better performance + responsiveness 👍**

# ☕ Java Multithreading — Thread Creation & Synchronization

---

## 🧠 What is a Thread?

> **Thread = smallest unit of execution (lightweight process)**

* Runs inside a process
* Shares memory/resources
* Java supports multithreading using `java.lang.Thread`

---

## 📌 Main Thread

👉 When a Java program starts:

* A **main thread** starts automatically
* It executes the `main()` method

---

## 🔍 Get Current Thread Name

```java id="t1"
System.out.println(Thread.currentThread().getName());
```

---

# ⚙️ Ways to Create Threads

---

## 1️⃣ Extending Thread Class

```java id="t2"
class MyThread1 extends Thread {
  public void run(){
    System.out.println("Thread 1 running: " + Thread.currentThread().getName());
  }
}
```

---

## 2️⃣ Implementing Runnable Interface

```java id="t3"
class MyThread2 implements Runnable {
  public void run(){
    System.out.println("Thread 2 running: " + Thread.currentThread().getName());
  }
}
```

---

# 🧪 Main Class Example

```java id="t4"
public class Test {
  public static void main(String[] args) throws InterruptedException {

    System.out.println("Main Thread: " + Thread.currentThread().getName());

    // Thread using extends
    MyThread1 thread1 = new MyThread1();

    // Thread using Runnable
    Thread thread2 = new Thread(new MyThread2());

    thread1.start();
    thread2.start();

    // Wait for both threads to finish
    thread1.join();
    thread2.join();

    System.out.println("Main thread finished");
  }
}
```

---

# 🔍 Output (Example)

```
Main Thread: main
Thread 1 running: Thread-0
Thread 2 running: Thread-1
Main thread finished
```

---

# 🤯 What is join()?

> `join()` makes main thread wait until other threads finish

---

# ⚠️ Shared Resource Problem

---

## ❌ Without Synchronization

```java id="t5"
class Counter {
  int count = 0;

  void increment(){
    count++;
  }
}
```

👉 Multiple threads updating `count` → wrong result ❌

---

# ✅ Using synchronized

```java id="t6"
class Counter {
  int count = 0;

  synchronized void increment(){
    count++;
  }
}
```

👉 Only one thread can access method at a time ✔

---

# 🧪 Shared Resource Example

```java id="t7"
class Counter {
  int count = 0;

  synchronized void increment(){
    count++;
  }
}

public class Test {
  public static void main(String[] args) throws InterruptedException {

    Counter counter = new Counter();

    Thread t1 = new Thread(() -> {
      for(int i=0; i<1000; i++){
        counter.increment();
      }
    });

    Thread t2 = new Thread(() -> {
      for(int i=0; i<1000; i++){
        counter.increment();
      }
    });

    t1.start();
    t2.start();

    t1.join();
    t2.join();

    System.out.println("Final Count: " + counter.count);
  }
}
```

---

## 🔍 Output

```
Final Count: 2000
```

---

# 🧠 Why synchronized?

* Prevents **race condition**
* Ensures **thread safety**
* Only one thread accesses critical section

---

# 🎯 Key Concepts

* Thread → execution unit
* start() → begins thread
* join() → wait for completion
* synchronized → control access

---

# 💬 Interview Line

> “Threads can be created by extending Thread class or implementing Runnable interface. Synchronization ensures that shared resources are accessed safely by multiple threads.”

---

# 🚀 Final Summary

* Create thread → `Thread` / `Runnable`
* Run → `start()`
* Wait → `join()`
* Protect data → `synchronized`

👉 **Multithreading = Concurrency + Control 👍**

``` 
