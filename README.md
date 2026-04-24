# ☕ Java OOP — Explained Simply (For Beginners)

Explained like never before -> Java from scratch to advanced — core concepts explained with real-life examples.  A structured learning repo covering OOP, Collections, Multithreading &amp; more.

---

## 📌 Table of Contents

- [Basics](#basics)
  - [What is OOP?](#what-is-oop)
  - [Class — The Blueprint](#class--the-blueprint)
  - [Object — The Real Thing](#object--the-real-thing)
  - [How to Create an Object](#how-to-create-an-object)

---

## Basics

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
