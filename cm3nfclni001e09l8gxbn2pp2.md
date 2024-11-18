---
title: "1.Fundamentals of Object oriented Programming"
seoDescription: "Discover the principles of structured, procedural, and object-oriented programming to enhance your coding proficiency and program organization"
datePublished: Mon Nov 18 2024 19:34:21 GMT+0000 (Coordinated Universal Time)
cuid: cm3nfclni001e09l8gxbn2pp2
slug: foundation
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/iOykDIkZLQw/upload/7f99f984cd1267242ae84011465ca736.jpeg
tags: programming-blogs, java, object-oriented-programming

---

## 1.1-Introduction, Basic Program Construction

---

### Unstructured Programming

* Unstructured Programming is a type of programming that generally executes in sequential order i.e., these programs just not jumped from any line of code and each line gets executed sequentially.
    
* It is also known as non-structured programming that is capable of creating turning-complete algorithms.
    
* Here “main program” is a sequence of commands or statements which modify data which is global throughout the whole program.
    
* This programming techniques provide tremendous disadvantages once the program gets sufficiently large.
    
* No re usability.
    

### Structured Programming

* [**Structured Programming**](https://www.geeksforgeeks.org/structured-programming-approach-with-advantages-and-disadvantages/) is a type of programming that generally converts large or complex programs into more manageable and small pieces of code.
    
* These small pieces of codes are usually known as [**functions**](https://www.geeksforgeeks.org/functions-in-c/) or modules or sub-programs of large complex programs.
    
* It is known as [**modular programming**](https://www.geeksforgeeks.org/modular-approach-in-programming/) and minimizes the chances of function affecting another.
    
* Structured programming is a kind of imperative programming where control flow is defined by nested loops, conditionals, and subroutines, rather than via gotos.
    

| **Structured Programming** | **Unstructured Programming** |
| --- | --- |
| It is basically a subset of procedural programs. | It is basically a procedural program. |
| In this, programmers are allowed to code a program simply by dividing the program into modules or smaller units. | In this, programmers are not allowed code divide programs into small units. Instead, the program should be written as a single continuous block without any breakage. |
| It is more user-friendly and easy to understand as compared to unstructured programming. | It is less user-friendly and little hard to understand as compared to structured programming. |
| It is easier to learn and follow. | It is difficult to learn and follow |
| Its advantages include reduce complexity, facilitate debugging, increase programmer productivity programs, etc. | Its advantages include its speed. |
| Such programs can be used for small and medium-scale projects and also for complex projects. | Such programs cannot be used for medium and complex projects. Instead, they can be used for small and easier projects. |
| These programs do not allow code duplication. | These programs allow code duplication. |
| Structured programs use a greater number of data types as compared to unstructured programs. | Unstructured programs use a limited number of data types as compared to structured programs. |
| It does not use [**GOTO**](https://www.geeksforgeeks.org/goto-statement-in-c-cpp/) to control the flow of execution. Instead, it uses loops. | It uses GOTO to control the flow of execution. |
| It produces readable code. | It hardly produces readable code. |
| It does not provide full freedom to programmers to program as they want. | It provides full freedom to programmers to program as they want. |

### Procedural Programming

**Procedural programming can be defined as pr**ogramming model which is derived from structured programming, based upon the concept of calling procedure. Procedures, also known as routines, subroutines or functions, simply consist of a series of computational steps to be carried out.

With procedural programming you can combine repeating sequences of statements into one single entity called a procedure

A procedure call is used to invoke the procedure.

The main program coordinates calls to procedures and hands over appropriate data as parameters.

Code reuse is possible.

Programs can now be written in a more structured and error free manner.

For example, if a procedure is correct, every time it is used it produces correct results.

### Modular Programming

Modular programming is the process of subdividing a computer program into separate sub-programs. A module is a separate software component. It can often be used in a variety of applications and functions with other components of the system.

With modular programming procedures of a common functionality are grouped together into separate modules.

A program therefore no longer consists of only one single part.

It is now divided into several smaller parts which interact through procedure calls and which form the whole program.

The main program coordinates calls to procedures in separate modules and hands over appropriate data as parameters.Each module can have its own data. This allows each module to manage an internal state which is modified by calls to procedures of this module. However, there is only one state per module and each module exists at most once in the whole program.

### Object-Oriented Programming (OOP)

Object-Oriented Programming can be defined as a programming model which is based upon the concept of objects. Objects contain data in the form of attributes and code in the form of methods. In object-oriented programming, computer programs are designed using the concept of objects that interact with the real world.

Organizing code around objects that represent real-world entities or concepts.

These objects have data (attributes) and behaviors (methods) that operate on that data.

Code is organized into classes that define the blueprint for objects and their behavior.

Objects are instances of classes.

Data is encapsulated within objects, protecting it from unauthorized access and modification.

Inheritance allows existing code to be reused and extended for new objects.

Encapsulation and interfaces further promote reusability.

Overview:

<table><tbody><tr><td colspan="1" rowspan="1"><p>Feature</p></td><td colspan="1" rowspan="1"><p>Procedural Programming</p></td><td colspan="1" rowspan="1"><p>Modular Programming</p></td><td colspan="1" rowspan="1"><p>Object-Oriented Programming (OOP)</p></td></tr><tr><td colspan="1" rowspan="1"><p>Focus</p></td><td colspan="1" rowspan="1"><p>Program logic flow</p></td><td colspan="1" rowspan="1"><p>Code reusability</p></td><td colspan="1" rowspan="1"><p>Real-world entities and their behavior</p></td></tr><tr><td colspan="1" rowspan="1"><p>Structure</p></td><td colspan="1" rowspan="1"><p>Linear sequence of functions</p></td><td colspan="1" rowspan="1"><p>Independent modules</p></td><td colspan="1" rowspan="1"><p>Classes and objects</p></td></tr><tr><td colspan="1" rowspan="1"><p>Data Organization</p></td><td colspan="1" rowspan="1"><p>Less emphasis on encapsulation</p></td><td colspan="1" rowspan="1"><p>Data encapsulation within modules</p></td><td colspan="1" rowspan="1"><p>Data encapsulated within objects</p></td></tr><tr><td colspan="1" rowspan="1"><p>Code Reusability</p></td><td colspan="1" rowspan="1"><p>Limited</p></td><td colspan="1" rowspan="1"><p>High emphasis</p></td><td colspan="1" rowspan="1"><p>High emphasis, with inheritance</p></td></tr></tbody></table>

I would like to express my gratitude for your interest in this article. I hope it has been informative and helpful. Your feedback is valuable to me, so please share your thoughts.