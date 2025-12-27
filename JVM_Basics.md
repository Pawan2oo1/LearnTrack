# JVM Basics

This document explains the core Java runtime concepts in simple language: JDK, JRE, JVM, bytecode, and the idea of "write once, run anywhere".

---

## 1. JDK, JRE, JVM

### JDK – Java Development Kit

The JDK is the **complete toolkit for Java developers**.  
It includes the Java compiler (`javac`), debugging tools, libraries, and the JRE so that programs can be compiled and run on the same machine.  
If you want to **develop** Java applications, you need the JDK.

### JRE – Java Runtime Environment

The JRE is used to **run** Java applications.  
It contains the JVM plus the standard Java libraries (core classes), but it **does not** include the compiler (`javac`), so it is meant for running programs, not building them.  
If you only want to **run** Java programs, the JRE is sufficient.

### JVM – Java Virtual Machine

The JVM is the **engine that actually executes Java programs**.  
It loads compiled `.class` files (bytecode), manages memory and garbage collection, handles thread execution, and translates bytecode into native machine instructions for the underlying operating system and hardware.  
The JVM acts as a layer of abstraction between Java code and the physical machine.

---

## 2. What is bytecode?

When a `.java` source file is compiled with the `javac` compiler, it is converted into a `.class` file that contains **bytecode**.  
Bytecode is a **platform-independent instruction format** that is understood by the JVM, not directly by the CPU.

Example flow:

```text
HelloWorld.java  --[javac compiler]-->  HelloWorld.class (bytecode)
                                              |
                                         [JVM reads]
                                              |
                                    Native machine code
```

The key insight is that **bytecode is not tied to any specific operating system or CPU**.  
Every JVM (on Windows, Linux, macOS, etc.) knows how to interpret the same bytecode and convert it to native instructions suitable for that platform.

---

## 3. What does "write once, run anywhere" mean?

"Write once, run anywhere" (WORA) describes Java's core strength: the **same compiled program** can run on different platforms without any modification.

A developer:

1. Writes Java source code (`.java` files) once.
2. Compiles it into bytecode (`.class` files) once using `javac`.
3. Distributes the bytecode.

Then, on any machine:

- Windows user with JVM installed can run the `.class` files.
- Linux user with JVM installed can run the **same** `.class` files.
- macOS user with JVM installed can run the **same** `.class` files.

This works because the **JVM is the bridge**: it reads the universal bytecode format and translates it into native instructions for whatever OS it is running on. The developer does not have to recompile or rewrite the program for each platform—just ship the bytecode once.

---

## 4. Summary

| Component    |       Purpose             |        Includes                      |
|-----------   |--------- |----------      |                                      |
| **JDK**      | Development toolkit       | Compiler, JRE, debugger, tools       |
| **JRE**      | Runtime environment       | JVM, libraries, JVM                  |
| **JVM**      | Java code execution engine| Bytecode interpreter, memory manager |

The flow: **Source code → Bytecode → JVM → Native code → OS execution**.

Because bytecode is universal and every JVM knows how to run it, Java achieves "write once, run anywhere".
