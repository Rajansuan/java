# ☕ Java — Explained Like Never Before

Explained like never before -> Java from scratch to advanced — core concepts explained with real-life examples. A structured learning repo covering OOP, Collections, Multithreading & more.

---

## Table of Contents

- [Basics](#basics)
  - [What is Java?](#what-is-java)
  - [How Java works](#how-java-works)
  - [How to install Java](#how-to-install-java)
  - [What is OOP?](#what-is-oop)
  - [Class — The Blueprint](#class--the-blueprint)
  - [Object — The Real Thing](#object--the-real-thing)
  - [How to Create an Object](#how-to-create-an-object)
- [Install IntelliJ and run your first Java program](#install-intellij-and-run-your-first-java-program)

---

## Basics

## What is Java?

Java is a programming language used to tell computers what to do.

Think like this:
- You write instructions = Java code
- Computer understands them after conversion

Java is also a platform because it gives you tools to turn code into a running program.

## How Java works

A Java program follows a simple process:

1. You write the code in files with .java extension.
2. The code gets compiled into bytecode, which is a special format that works on any computer.
3. The JVM runs the bytecode by turning it into instructions that your specific computer can understand, so the program works on Windows, Mac, Linux, etc.


| Pipeline | Description |
|---:|---|
| .java (source code) <br> ↓ <br> javac (compiler) <br> ↓ <br> .class (bytecode) <br> ↓ <br> JVM (interpreter + JIT) <br> ↓ <br> Machine Code (runs on OS) | .java: human-readable source you write. <br> javac: compiles source into bytecode. <br> .class: platform-independent bytecode. <br> JVM: loads bytecode, interprets and JIT-compiles hot code. <br> Machine Code: native CPU instructions executed by the OS/hardware. |

## JDK, JRE, JVM — what are they?

- **JVM** = Java Virtual Machine
  - It runs Java bytecode.
  - It is the part that works on Windows, Mac, or Linux.
  - JVM is like the machine that understands the code.

- **JRE** = Java Runtime Environment
  - It has the JVM plus the standard Java libraries.
  - It is enough to run Java programs.
  - JRE is like the kitchen with the stove and ingredients.

- **JDK** = Java Development Kit
  - It has the JRE plus tools to write and compile Java code.
  - It is what you need to make Java programs.
  - JDK is like a full kitchen with tools, stove, ingredients, and recipe books.

Important tools in the JDK:
- `javac` — compiler that turns `.java` code into `.class` bytecode
- `java` — launcher that starts the JVM and runs the bytecode
- `jar` — packages Java files into one archive

## How to install Java

When someone says “install Java,” they usually mean “install the JDK.”

- On Mac:
  - Use Homebrew: `brew install --cask temurin`
- On Windows:
  - Download an OpenJDK package such as Eclipse Temurin
- On Linux:
  - Use the package manager, for example: `sudo apt install openjdk-17-jdk`

After installation, check:

```bash
java -version
javac -version
```

## What is OOP?

OOP stands for **Object Oriented Programming**.

Think of the real world — everything around you is an **object**:
- A Dog has a name, color, age → and can bark, eat, run
- A Car has a brand, color, speed → and can drive, stop, honk

Java organizes code the **same way** — using objects that have **properties** and **behaviors**.

---

## Class — The Blueprint

A **Class** is just a **blueprint**. It's not the real thing yet — it's just a plan.

> Think of it like a **house plan on paper**. The plan exists, but no one lives in it yet.

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

## Object — The Real Thing

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

## How to Create an Object

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

## Basic Java program — skeleton

```java
class Dog {
    public static void main(String[] args) {
        System.out.println("Hello World");
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

## Install IntelliJ and run your first Java program

Quick overview: install IntelliJ IDEA, attach a JDK, create a project, add a class with main, then run it.

1) Install IntelliJ IDEA
- Mac: Download from https://www.jetbrains.com/idea/download or use Homebrew
- Windows / Linux: Download the Community edition from JetBrains page and install.

2) Make sure JDK is available
- Option A: Install a JDK separately (recommended). Example (Mac / Linux):
  - brew install --cask temurin   (Mac)
  - sudo apt install openjdk-17-jdk   (Linux)
- Option B: Let IntelliJ download a JDK when creating a project.
- Verify on terminal:
  - java -version
  - javac -version

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
        System.out.println("Hello World");
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





