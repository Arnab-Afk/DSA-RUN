---
title: "PYQ- Solutions"
seoTitle: "Past Years' Question Solutions"
seoDescription: "Explore Java's platform independence, compare abstract classes and interfaces, understand packages, and more in this comprehensive solutions guide"
datePublished: Wed Nov 20 2024 17:52:01 GMT+0000 (Coordinated Universal Time)
cuid: cm3q6kpff000w09l80d6yeec4
slug: pyq-solutions
tags: object-oriented-programming, array-methods

---

---

### Q.1 “Java is platform independent” , Is this True? Justify or contradict your statement.

Yes, Java is platform-independent. This is one of its key strengths, enabling "Write Once, Run Anywhere" (WORA) functionality.

Here's how it works:

1. **Compilation:** When you compile Java code, it's not directly translated into machine code specific to a particular operating system or architecture. Instead, it's compiled into bytecode, a platform-independent intermediate code.
    
2. **Java Virtual Machine (JVM):** The bytecode is executed by a JVM, which acts as a virtual machine. The JVM is responsible for translating the bytecode into machine code that can be understood by the specific operating system and hardware.
    

**Therefore, as long as a system has a compatible JVM installed, it can run Java applications, regardless of the underlying platform (Windows, macOS, Linux, etc.).**

**However, it's important to note that the JVM itself is platform-dependent.** Different JVMs exist for different operating systems. So, while Java applications are platform-independent, the JVM that executes them is not.

**In essence, Java's platform independence is achieved through the combination of bytecode and the JVM.**

---

### Q.2 Compare abstract class and interface in java, with the help of an example of each and three important points of difference.

**Abstract Classes vs. Interfaces in Java**

Abstract classes and interfaces are two important constructs in Java that provide a way to achieve abstraction and code reusability. However, they have distinct characteristics and use cases.

**Key Differences:**

1. **Inheritance:**
    
    * **Abstract Classes:** A class can extend only one abstract class.
        
    * **Interfaces:** A class can implement multiple interfaces.
        
2. **Method Implementation:**
    
    * **Abstract Classes:** Can contain both abstract and concrete methods.
        
    * **Interfaces:** Can only contain abstract methods and default methods (since Java 8).
        
3. **Variables:**
    
    * **Abstract Classes:** Can contain both static and non-static variables.
        
    * **Interfaces:** Can only contain static final variables.
        

**Example: Abstract Class**

Java

```java
abstract class Shape {
    abstract void draw();

    public void erase() {
        System.out.println("Erasing shape");
    }
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a circle");
    }
}
```

**Example: Interface**

Java

```java
interface Drawable {
    void draw();
}

class Rectangle implements Drawable {
    @Override
    public void draw() {
        System.out.println("Drawing a rectangle");
    }
}
```

**When to Use Which:**

* **Abstract Classes:**
    
    * When you want to define a partial implementation of a class.
        
    * When you want to provide a common base class for a group of related classes.
        
    * When you want to define a set of methods that subclasses must implement, but also provide some default implementations.
        
* **Interfaces:**
    
    * When you want to define a contract that multiple unrelated classes can implement.
        
    * When you want to achieve multiple inheritance of types.
        
    * When you want to design highly decoupled components.
        

In summary, abstract classes and interfaces are powerful tools for creating reusable and maintainable code in Java. By understanding their differences and use cases, you can make informed decisions about when to use each.

---

### Q.3 What are packages? Why are they useful? Give the syntax and brief example of creating and using packages.

A set of classes and interfaces grouped together are known as Packages in JAVA. The name itself defines that pack (group) of related types such as classes, sub-packages, enumeration, annotations, and interfaces that provide name-space management. Every class is a part of a certain package. When you need to use an existing class, you need to add the package within the Java program.

Packages help organize your Java code and prevent naming conflicts.A **java package** is a group of similar types of classes, interfaces and sub-packages.

Package in java can be categorized in two form, built-in package and user-defined package.There are many built-in packages such as java, lang, awt, javax, swing, net, io, util, sql etc.

The benefits of using Packages in Java are as follows:

* The packages organize the group of classes into a single API unit
    
* It will control the naming conflicts
    
* The access protection will be easier. Protected and default are the access level control to the package
    
* Easy to locate the related classes
    
* Reuse the existing classes in packages
    

User-defined packages are bundles of groups of classes or interfaces created by the programmer for their purpose.

You need the help of the keyword “package” to create your own package. The declaration of the package should be the first statement before any import statements in the Java class.

Let us consider our example of a User-defined package - University.Department.Staff.

```java
//create a user defined package university
package university;
public class WelcomeMessage
{
public void ShowMessage(){
        System.out.println("Welcome to our University");
    }
}
```

---

### What are static methods? Give and example of calling a static method.

The static keyword is used to construct methods that will exist regardless of whether or not any instances of the class are generated. Any method that uses the static keyword is referred to as a static method.

**Features of static method:**

* A static method in Java is a method that is part of a class rather than an instance of that class.
    
* Every instance of a class has access to the method.
    
* Static methods have access to class variables (static variables) without using the class’s object (instance).
    
* Only static data may be accessed by a static method. It is unable to access data that is not static (instance variables).
    
* In both static and non-static methods, static methods can be accessed directly.
    

A program to demonstrate the use of Static Method:

```java
    //Java Program to demonstrate the use of a static method.  
    class Student{  
         int rollno;  
         String name;  
         static String college = "ITS";  
         //static method to change the value of static variable  
         static void change(){  
         college = "BBDIT";  
         }  
         //constructor to initialize the variable  
         Student(int r, String n){  
         rollno = r;  
         name = n;  
         }  
         //method to display values  
         void display(){System.out.println(rollno+" "+name+" "+college);}  
    }  
    //Test class to create and display the values of object  
    public class TestStaticMethod{  
        public static void main(String args[]){  
        Student.change();//calling change method  
        //creating objects  
        Student s1 = new Student(111,"Karan");  
        Student s2 = new Student(222,"Aryan");  
        Student s3 = new Student(333,"Sonoo");  
        //calling display method  
        s1.display();  
        s2.display();  
        s3.display();  
        }  
    }
```

---

### Java is a strongly typed language. Is it true? Justify or contradict this statement accordingly.

A strongly typed programming language is one in which each type of data, such as integers, characters, hexadecimals and packed decimals, is predefined as part of the programming language, and all constants or variables defined for a given program must be described with one of the data types. Certain operations might be allowable only with specific data types.

Java is considered strongly typed because it demands the declaration of every variable with a data type. Users cannot create a variable without the range of values it can hold. Once declared, the data type of the variable cannot be changed.

A key advantage of strong data typing is that it enforces a rigorous set of rules to ensure a certain consistency of results. Further, a compiler can quickly detect an object being sent a message to which it will not respond, preventing runtime errors. Other benefits include no runtime penalties for determining types, accelerated development by detecting errors earlier and better-optimized code from the compiler.

Java doesn’t allow **automatic type coercion**. This means that the data type for each variable must be specified explicitly by the programmer, and any attempt to assign a value of a different type to a variable will result in a **compile-time error**.

---

### How is memory allocated to objects in Java ?

In Java, all objects are dynamically allocated on Heap. This is different from C++ where objects can be allocated memory either on Stack or on Heap. In JAVA, when we allocate the object using the "**new keyword**", the object is allocated on Heap, otherwise on Stack if not global or static.

When we only declare a variable of a class type, only a reference is created (memory is not allocated for the object). To allocate memory to an object, we must use the "**new keyword**". So the object is always allocated memory on the heap.

The creation of an object is a two-step procedure where we first declare an object of that class type and then a physical copy of the actual object of the class is assigned to that variable.

This assignment of an actual copy of the object is done by using the "**new keyword"** for the dynamic allocation of memory. A "**new keyword**" allocates memory in the heap and the reference to the allocated object is nothing but an address stored in the variable of the respective reference type.

---

### Write a Java program for the following problem statement: Given an array of integers nums and an integer target. return indices of the two numbers such that they add up to target. You may assume that each input would have exactly one solution, and you may not use the same element twice. You can return the answer in any order. Example: Input: nums target = 9 Output: \[0, 1\] Because nums \[0\] + nums \[1\]= 9. we return 0, 1.

```java
import java.util.Scanner;


public class test {
    public static int[] add(int nums[], int target) {
        int result[] = new int[2];
        for(int i=0; i<nums.length; i++) {
            for(int j=i+1; j<nums.length; j++) {
                if(nums[i] + nums[j] == target) {
                    result[0] = i;
                    result[1] = j;
                    return result;

                }
            }
        }
        return result;
    }
    
    
    public static void main(String[] args) {
       int nums[] = {1, 2, 3, 4, 5};
       int target = 5;
       int result[] = add(nums, target);
       System.out.println(nums[result[0]] + " " + nums[result[1]]);
    }
}
```

---

### Write a Java program for the following problem state;nent: Given an integer array nums of length n, you want to create an array ans of length 2n where ans\[i\] ==nums\[i\] and ans\[i + n\] == nums\[i\] for 0 &lt;= i &lt; n. Return the array ans. Your program should take the input from the user and display the output to the user.

```java
import java.util.*;

public class test2 {
    
    public static int[] ans(int nums[]) {
        int[] ans = new int[nums.length*2];
        for(int i=0; i<nums.length; i++) {
            ans[i] = nums[i];
            ans[i+nums.length] = nums[i];
        }
        return ans;
    }

    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the number of elements in the array: ");
        int n= sc.nextInt();

        int nums[] = new int[n];
        System.out.println("Size of array is : " + n);
        for(int i=0; i<n; i++) {
            System.out.println("Enter the element at index " + i + ": ");
            nums[i] = sc.nextInt();
        }
        int ans[] = ans(nums);
        for(int i=0; i<ans.length; i++) {
            System.out.print(ans[i] + " ");
        }
    }

}
```

---

### Write a program that creates two threads. Both execute a loop with 10 iterations. One thread generates squares of number from 1 to 10. Another thread generates cubes of numbers from I to 10. Both of them store their results in a shared array in the order: square followed by cube. So the array will contain : 1 1 48 9 27 ...100 1000. Use the synchronized keyword.

```java
public class test3 {
    private static final int IO = 10; 
    private static final int[] sharedArray = new int[2 * IO]; 
    private static int index = 0; 

    static class Task implements Runnable {
        private final boolean generateSquare; 

        public Task(boolean generateSquare) {
            this.generateSquare = generateSquare;
        }

        @Override
        public void run() {
            for (int i = 1; i <= 10; i++) {
                int value = generateSquare ? i * i : i * i * i;
                synchronized (sharedArray) {
                    sharedArray[index++] = value;
                }
            }
        }
    }
    public static void main(String[] args) {
        
        Runnable squareTask = new Task(true);  // Task for squares
        Runnable cubeTask = new Task(false);  // Task for cubes

        
        Thread squareThread = new Thread(squareTask);
        Thread cubeThread = new Thread(cubeTask);

        
        squareThread.start();
        cubeThread.start();

        
        try {
            squareThread.join();
            cubeThread.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        
        System.out.println("Shared Array:");
        for (int num : sharedArray) {
            System.out.print(num + " ");
        }
    }
}
```

---

### Write a Java program that takes job applicants' data including their name, age and address (PIN code) as input and stores it in an array. Define two exceptions called "IncorrectName" which will be thrown if there are any non-alphabetic characters in name, and "IncorrectAddress' which will be thrown if the PIN code is not in correct format (6 digit integer). Use these exceptions when you are validating input in your program.

```java
import java.util.*;


class InvalidNameException extends Exception {
    public InvalidNameException(String message) {
        super(message);
    }
}
class InvalidIdException extends Exception {
    public InvalidIdException(String message) {
        super(message);
    }
}
class Applicants {
    String name;
    int age;
    int id;
    public Applicants(String name, int age, int id) {
        this.name = name;
        this.age = age;
        this.id = id;
        
       
    }

}

public class test4 {
    private static void validateName(String name) throws InvalidNameException {
        for (char c : name.toCharArray()) {
            if (Character.isDigit(c)) {
                throw new InvalidNameException("Name cannot contain numbers.");
            }
        }
    }
    private static void validateId(int id) throws InvalidIdException {
        if (String.valueOf(id).length() != 6) {
            throw new InvalidIdException("ID must be exactly 6 digits.");
        }
    }
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the number of applicants: ");
        int n = sc.nextInt();
        Applicants[] applicants = new Applicants[n];
        for (int i = 0; i < n; i++) {
            try {
            System.out.println("Enter the name of applicant " + (i + 1) + ":");
            String name = sc.next();
            validateName(name);
            System.out.println("Enter the age of applicant " + (i + 1) + ": ");
            int age = sc.nextInt();
            System.out.println("Enter the id of applicant " + (i + 1) + ":");
            int id = sc.nextInt();
            validateId(id);
            Applicants applicant = new Applicants(name, age, id);
            applicants[i] = applicant;
            }
            catch (InvalidNameException | InvalidIdException e) {
                System.out.println(e.getMessage());
                i--; 
            }
        }
    }
}
```

---

### Write a program which stores information about n students in a two dimensional array. The array should contain number of rows equal to number of students. Each row will have number of columns equal to number of semesters by that student which may vary from student to student. The program should display student number (index +1),percentage scored by that student in each semester and its average percentage as output. (It is expected to assign columns to each row dynamically after getting no of semesters value from user)

```java
import java.util.Scanner;

public class test5 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the number of applicants: ");
        int n = sc.nextInt();
        int [][] scores= new int[n][];
        for(int i=0;i<n;i++){
            System.out.println("Enter number of semesters for this student: ");
            int numSemesters = sc.nextInt();
            scores[i] = new int[numSemesters];
            for (int j = 0; j < numSemesters; j++) {
                System.out.println("Enter percentage for Student "+(i + 1) + "Semester: "+ (j + 1));
                scores[i][j] = sc.nextInt();
            }
        }
        displayResults(scores);
        sc.close();
        }
        public static void displayResults(int[][] performances) {
            System.out.println("\n--- Student Performance Summary ---");
            for (int i = 0; i < performances.length; i++) {
                    double totalPercentage = 0;
                // Print student number and semester percentages
                System.out.printf("Student %d: ", (i + 1));
                for (int j = 0; j < performances[i].length; j++) {
                    System.out.printf("Sem %d: %.2f%% ", (j + 1), performances[i][j]);
                        totalPercentage += performances[i][j];
                }
                double averagePercentage = totalPercentage / performances[i].length;
                System.out.printf("| Average: %.2f%%\n", averagePercentage);
    
            }
        
    }
}
```

---

Write a program which accepts information about n no of students from user .Create an array of objects to store student\_id,name,avg\_marks. Your program should provide following functionalities

1.To add student

2.To delete any student detail

3\. To display student details.

```java
import java.util.Scanner;
import java.util.ArrayList;

class Student {
    int id;
    String name;
    int avg_marks;

    public Student(int id, String name, int avg_marks) {
        this.id = id;
        this.name = name;
        this.avg_marks = avg_marks;
    }

}
public class test6 {
    
    public static void add(int id, String name, int avg_marks, Student[] students, int index) {
        Student student = new Student(id, name, avg_marks);
        students[index] = student;
        System.out.println("Student added successfully!");
    }
    
    public static void delete(int id, Student[] students) {
        for (int i = 0; i < students.length; i++) {
            if (students[i] != null && students[i].id == id) {
                students[i] = null;
                System.out.println("Student deleted successfully!");
                return;
            }
        }
        System.out.println("Student not found!");
    }

    public static void display(Student[] students) {
        for (Student student : students) {
            if (student != null) {
                System.out.println("ID: " + student.id + ", Name: " + student.name + ", Average Marks: " + student.avg_marks);
            }
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the number of students: ");
        int n = sc.nextInt();
        Student[] students = new Student[n];
        boolean status = true;

        while (status) {
            System.out.println("1. Add student\n2. Delete student\n3. Display students\n4. Exit\nEnter your choice: ");
            int choice = sc.nextInt();
            switch (choice) {
                case 1:
                    for (int i = 0; i < n; i++) {
                        if (students[i] == null) {
                            System.out.println("Enter the id of student " + (i + 1) + ":");
                            int id = sc.nextInt();
                            System.out.println("Enter the name of student " + (i + 1) + ":");
                            String name = sc.next();
                            System.out.println("Enter the average marks of student " + (i + 1) + ":");
                            int avg_marks = sc.nextInt();
                            add(id, name, avg_marks, students, i);
                            break;
                        }
                    }
                    break;
                case 2:
                    System.out.println("Enter the id of the student to delete: ");
                    int id = sc.nextInt();
                    delete(id, students);
                    break;
                case 3:
                    display(students);
                    break;
                case 4:
                    status = false;
                    break;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
        sc.close();
    }
}
```

---

### Write a program to accept n number of strings from the user and sort them in alphabetical order.

```java
import java.util.*;
//•	Write a program to accept n number of strings from the user and sort them in alphabetical order.
public class test7 {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the number of strings in the array: ");
        int n = sc.nextInt();
        String[] strings = new String[n];
        System.out.println("Size of array is : " + n);
        for (int i = 0; i < n; i++) {
            System.out.println("Enter string in position: " + (i+1) );
            
            strings[i] = sc.next();
        }
        Arrays.sort(strings);

        System.out.println("Strings in alphabetical order : ");
        for(int i=0; i<n; i++) {
            System.out.println(strings[i]);
        }
    }
}
```

---

### Write a program to accept string from the user and ask user whether he/she wants to modify that string, if yes accept the substring with the index value and then calculate and display number of vowels in it.

```java
import java.util.*;

public class test8 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter a string: ");
        String str = sc.nextLine();
        System.out.println("Do you want to modify the string? (yes/no)");
        String choice = sc.next();
        String newStr = str;
        if(choice.equals("yes")) {
            System.out.println("Enter the start index to update: ");
            int start = sc.nextInt();
            System.out.println("Enter the end index to update: ");
            int end = sc.nextInt();
            System.out.println("Enter the new string to update: ");
            String substr = sc.next();
            newStr = str.substring(0, start) + substr + str.substring(end);
        } else {
            System.out.println("You chose not to modify the string.");
        }
        
        int vowelCount = countVowels(newStr);
        System.out.println("The number of vowels in the string is: " + vowelCount);
    }

    public static int countVowels(String str) {
        int count = 0;
        System.out.println("The string is: " + str);
        for (char c : str.toLowerCase().toCharArray()) {
            if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u') {
                count++;
            }
        }
        return count;
    }
}
```

---

hi

```java
import java.util.*;

class Shopping {
    String name;
    int price;
    int quantity;

    public Shopping(String name, int price, int quantity) {
        this.name = name;
        this.price = price;
        this.quantity = quantity;
        
    }
}

public class test9 {
    public static void add(String name, int price, int quantity, Vector<Shopping> here) {
        Shopping item = new Shopping(name, price, quantity);
        here.add(item);
        System.out.println("Item added successfully!");
    }

    public static void display(Vector<Shopping> here) {
        for (int i = 0; i < here.size(); i++) {
            Shopping item = here.get(i);
            System.out.println("Name: " + item.name + " Price: " + item.price + " Quantity: " + item.quantity);
        }
    }

    public static void remove(String name, Vector<Shopping> here) {
        for (int i = 0; i < here.size(); i++) {
            Shopping item = here.get(i);
            if (item.name.equals(name)) {
                here.remove(i);
                System.out.println("Item removed successfully!");
                return;
            }
        }
        System.out.println("Item not found!");
    }

    public static void main(String[] args) {
        Vector<Shopping> items = new Vector<>();
        Scanner sc = new Scanner(System.in);
        boolean status = true;
        while (status) {
            System.out.println("1. Add an item\n2. Remove an item\n3. Display all items\n4. Exit\nEnter your choice: ");
            int index = sc.nextInt();
            switch (index) {
                case 1:
                    System.out.println("Enter the name of the item: ");
                    String name = sc.next();
                    System.out.println("Enter the price of the item: ");
                    int price = sc.nextInt();
                    System.out.println("Enter the quantity of the item: ");
                    int quantity = sc.nextInt();
                    add(name, price, quantity, items);
                    break;
                case 2:
                    System.out.println("Enter the name of the item to remove: ");
                    String remove = sc.next();
                    remove(remove, items);
                    break;
                case 3:
                    System.out.println("Items in the list: ");
                    display(items);
                    break;
                case 4:
                    status = false;
                    break;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
        sc.close();
    }
}
```

---

### Implement a menu driven program  for the following:

Accepts a shopping list (name, price and quantity)from the command line and stores them in a vector.

To delete specific item (given by user) in the vector

Add item at the end of the vector

Add item at specific location

Print the contents of vector using enumeration interface.

```java
import java.util.*;

class Shopping {
    String name;
    int price;
    int quantity;

    public Shopping(String name, int price, int quantity) {
        this.name = name;
        this.price = price;
        this.quantity = quantity;
        
    }
}

public class test9 {
    public static void add(String name, int price, int quantity, Vector<Shopping> here) {
        Shopping item = new Shopping(name, price, quantity);
        here.add(item);
        System.out.println("Item added successfully!");
    }

    public static void display(Vector<Shopping> here) {
        for (int i = 0; i < here.size(); i++) {
            Shopping item = here.get(i);
            System.out.println("Name: " + item.name + " Price: " + item.price + " Quantity: " + item.quantity);
        }
    }

    public static void remove(String name, Vector<Shopping> here) {
        for (int i = 0; i < here.size(); i++) {
            Shopping item = here.get(i);
            if (item.name.equals(name)) {
                here.remove(i);
                System.out.println("Item removed successfully!");
                return;
            }
        }
        System.out.println("Item not found!");
    }

    public static void main(String[] args) {
        Vector<Shopping> items = new Vector<>();
        Scanner sc = new Scanner(System.in);
        boolean status = true;
        while (status) {
            System.out.println("1. Add an item\n2. Remove an item\n3. Display all items\n4. Exit\nEnter your choice: ");
            int index = sc.nextInt();
            switch (index) {
                case 1:
                    System.out.println("Enter the name of the item: ");
                    String name = sc.next();
                    System.out.println("Enter the price of the item: ");
                    int price = sc.nextInt();
                    System.out.println("Enter the quantity of the item: ");
                    int quantity = sc.nextInt();
                    add(name, price, quantity, items);
                    break;
                case 2:
                    System.out.println("Enter the name of the item to remove: ");
                    String remove = sc.next();
                    remove(remove, items);
                    break;
                case 3:
                    System.out.println("Items in the list: ");
                    display(items);
                    break;
                case 4:
                    status = false;
                    break;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
        sc.close();
    }
}
```

---

Thank You :)

Drop Questions in comments.