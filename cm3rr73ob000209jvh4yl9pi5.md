---
title: "Sample Questions"
seoTitle: "Practice Quiz Questions"
seoDescription: "Java tasks: create custom classes, practice multi-threading, and perform array operations to improve coding skills"
datePublished: Thu Nov 21 2024 20:17:04 GMT+0000 (Coordinated Universal Time)
cuid: cm3rr73ob000209jvh4yl9pi5
slug: sample-questions
tags: object-oriented-programming

---

### Create a custom Product class with name, price, and quantity fields. Create an ArrayList of Product objects and sort it based on price in ascending order. create functions to add delete display product

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.Scanner;

class Product {
    String name;
    double price;
    int quantity;

    public Product(String name, double price, int quantity) {
        this.name = name;
        this.price = price;
        this.quantity = quantity;
    }

    public double getPrice() {
        return price;
    }

    @Override
    public String toString() {
        return "Product{" +
                "name='" + name + '\'' +
                ", price=" + price +
                ", quantity=" + quantity +
                '}';
    }
}

public class Main {
    static ArrayList<Product> products = new ArrayList<>();
    static Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int choice;

        do {
            System.out.println("\nProduct Management System");
            System.out.println("1. Add Product");
            System.out.println("2. Delete Product");
            System.out.println("3. Display Products");
            System.out.println("4. Sort Products by Price");
            System.out.println("5. Exit");
            System.out.print("Enter your choice: ");

            choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    addProduct();
                    break;
                case 2:
                    deleteProduct();
                    break;
                case 3:
                    displayProducts();
                    break;
                case 4:
                    sortProductsByPrice();
                    break;
                case 5:
                    System.out.println("Exiting program...");
                    break;
                default:
                    System.out.println("Invalid choice!");
            }
        } while (choice != 5);
    }

    private static void addProduct() {
        System.out.print("Enter product name: ");
        String name = scanner.next();

        System.out.print("Enter product price: ");
        double price = scanner.nextDouble();

        System.out.print("Enter product quantity: ");
        int quantity = scanner.nextInt();

        products.add(new Product(name, price, quantity));
        System.out.println("Product added successfully!");
    }

    private static void deleteProduct() {
        if (products.isEmpty()) {
            System.out.println("No products to delete!");
            return;
        }

        System.out.print("Enter product name to delete: ");
        String name = scanner.next();

        products.removeIf(product -> product.name.equals(name));

        System.out.println("Product deleted successfully!");
    }

    private static void displayProducts() {
        if (products.isEmpty()) {
            System.out.println("No products to display!");
            return;
        }

        System.out.println("\nProduct Details:");
        for (Product product : products) {
            System.out.println(product);
        }
    }

    private static void sortProductsByPrice() {
        Collections.sort(products, Comparator.comparingDouble(Product::getPrice));
        System.out.println("Products sorted by price:");
        displayProducts();
    }
}
```

---

### Given a vector of integers, find the pair of elements whose sum is closest to a given target value. Input: vector = {10, 22, 28, 29, 30, 40}, target = 54 Output: 22 and 30

```java
import java.util.*;

public class Main {
    public static int[] findClosestPair(int[] arr, int target) {
        // Sort the array first
        Arrays.sort(arr);
        
        // Initialize variables
        int n = arr.length;
        int left = 0;
        int right = n - 1;
        int closestSum = Integer.MAX_VALUE;
        int[] result = new int[2];
        
        // Two-pointer approach
        while (left < right) {
            int currentSum = arr[left] + arr[right];
            
            // If current sum exactly matches target, return immediately
            if (currentSum == target) {
                return new int[]{arr[left], arr[right]};
            }
            
            // Update closest sum if current sum is closer to target
            if (Math.abs(currentSum - target) < Math.abs(closestSum - target)) {
                closestSum = currentSum;
                result[0] = arr[left];
                result[1] = arr[right];
            }
            
            // Move pointers based on sum comparison
            if (currentSum < target) {
                left++;
            } else {
                right--;
            }
        }
        
        return result;
    }
    
    public static void main(String[] args) {
        int[] vector = {10, 22, 28, 29, 30, 40};
        int target = 54;
        
        int[] closestPair = findClosestPair(vector, target);
        
        System.out.println("Closest pair: " + closestPair[0] + " and " + closestPair[1]);
        System.out.println("Sum: " + (closestPair[0] + closestPair[1]));
    }
}
```

---

### Write a java program that implements a multi-thread application that has three threads. First thread generates a random integer every 1 second and if the value is even, the second thread computes the square of the number and prints. If the value is odd, the third thread will print the value of the cube of the number.

```java
import java.util.Random;

public class MultiThreadApp {
    // Shared variable to store the generated number
    private static int number;

    // First Thread - Number Generator
    static class NumberGeneratorThread implements Runnable {
        @Override
        public void run() {
            Random random = new Random();
            while (true) {
                // Generate random number
                number = random.nextInt(100);
                System.out.println("Generated Number: " + number);
                
                try {
                    Thread.sleep(1000); // Sleep for 1 second
                } catch (InterruptedException e) {
                    break;
                }
            }
        }
    }

    // Second Thread - Even Number Processor (Square)
    static class EvenNumberThread implements Runnable {
        @Override
        public void run() {
            while (true) {
                // Check if number is even
                if (number % 2 == 0) {
                    System.out.println("Square of " + number + " is: " + (number * number));
                }
                
                try {
                    Thread.sleep(1000); // Wait a bit before next check
                } catch (InterruptedException e) {
                    break;
                }
            }
        }
    }

    // Third Thread - Odd Number Processor (Cube)
    static class OddNumberThread implements Runnable {
        @Override
        public void run() {
            while (true) {
                // Check if number is odd
                if (number % 2 != 0) {
                    System.out.println("Cube of " + number + " is: " + (number * number * number));
                }
                
                try {
                    Thread.sleep(1000); // Wait a bit before next check
                } catch (InterruptedException e) {
                    break;
                }
            }
        }
    }

    public static void main(String[] args) {
        // Create threads
        Thread generatorThread = new Thread(new NumberGeneratorThread());
        Thread evenThread = new Thread(new EvenNumberThread());
        Thread oddThread = new Thread(new OddNumberThread());

        // Start threads
        generatorThread.start();
        evenThread.start();
        oddThread.start();
    }
}
```

---

### Write a program in Java to create two threads thread A and thread B. Thread A stores an array of characters whereas Thread B stores an array of numbers. Make them run concurrently and display characters and numbers

```java
public class Main {
    public static void main(String[] args) {
        // Thread A - Character Thread
        Thread charThread = new Thread(() -> {
            char[] characters = {'A', 'B', 'C', 'D', 'E'};
            
            for (char ch : characters) {
                System.out.println("Character: " + ch);
                try {
                    Thread.sleep(500); 
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        });


        Thread numberThread = new Thread(() -> {
            int[] numbers = {1, 2, 3, 4, 5};
            
            for (int num : numbers) {
                System.out.println("Number: " + num);
                try {
                    Thread.sleep(500); 
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        });


        charThread.start();
        numberThread.start();

        try {
            charThread.join();
            numberThread.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}
```

---

### Write a program to create two threads Thread A and Thread B. Thread A displays the numbers from 1 to 7 and thread B displays days in a week. Create main method to call these two threads and display the output.

```java
public class Main {
    // Shared resource for synchronization
    static class SharedResource {
        private boolean isNumberTurn = true;

        // Synchronized method 
        public synchronized void printNumber() {
            for (int i = 1; i <= 7; i++) {
                while (!isNumberTurn) {
                    try {
                        wait();
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                }
                
                System.out.println("Number Thread: " + i);
                isNumberTurn = false;
                notify();
            }
        }

        public synchronized void printDays() {
            String[] days = {
                "Monday", 
                "Tuesday", 
                "Wednesday", 
                "Thursday", 
                "Friday", 
                "Saturday", 
                "Sunday"
            };

            for (String day : days) {
                while (isNumberTurn) {
                    try {
                        wait();
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                }
                
                System.out.println("Days Thread: " + day);
                isNumberTurn = true;
                notify();
            }
        }
    }

    public static void main(String[] args) {
        SharedResource resource = new SharedResource();

        Thread numberThread = new Thread(() -> {
            resource.printNumber();
        });

        Thread daysThread = new Thread(() -> {
            resource.printDays();
        });

        numberThread.start();
        daysThread.start();

        try {
            numberThread.join();
            daysThread.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}
```

---

### Problem: Split an array between two threads

**Thread A: Calculate sum of first half**

**Thread B: Calculate sum of second half**

**Main thread combines and prints total sum**

```java
public class Main {
    // Shared result array to store partial sums
    private static int[] partialSums = new int[2];
    
    // Runnable for calculating first half sum
    static class FirstHalfSumRunnable implements Runnable {
        private int[] array;
        
        public FirstHalfSumRunnable(int[] array) {
            this.array = array;
        }
        
        @Override
        public void run() {
            int sum = 0;
            for (int i = 0; i < array.length / 2; i++) {
                sum += array[i];
            }
            partialSums[0] = sum;
        }
    }
    
    // Runnable for calculating second half sum
    static class SecondHalfSumRunnable implements Runnable {
        private int[] array;
        
        public SecondHalfSumRunnable(int[] array) {
            this.array = array;
        }
        
        @Override
        public void run() {
            int sum = 0;
            for (int i = array.length / 2; i < array.length; i++) {
                sum += array[i];
            }
            partialSums[1] = sum;
        }
    }
    
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
        
        Runnable firstHalfTask = new FirstHalfSumRunnable(array);
        Runnable secondHalfTask = new SecondHalfSumRunnable(array);
        
        Thread threadA = new Thread(firstHalfTask);
        Thread threadB = new Thread(secondHalfTask);
        
        threadA.start();
        threadB.start();
        
        try {
            threadA.join();
            threadB.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        
        int firstHalfSum = partialSums[0];
        int secondHalfSum = partialSums[1];
        int totalSum = firstHalfSum + secondHalfSum;
        
        System.out.println("First Half Sum: " + firstHalfSum);
        System.out.println("Second Half Sum: " + secondHalfSum);
        System.out.println("Total Sum: " + totalSum);
    }
}
```

---

Thank you :)