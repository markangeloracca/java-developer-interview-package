## MY INTRODUCTION

Hello, thank you for joining me today. My name is Mark Angelo Racca known as Reach, and I'll be one of the Engineers doing the technical interview. I'm a Senior Java Engineer with over 15 years of experience in software development. For the past three and a half years, I've been with ING, specifically within the WBTech Lending tribe. While ING is my first experience in the banking sector, I also bring three years of experience from the fast-paced world of FinTech. I'm looking forward to our discussion and understanding your technical skills... and also be able to assess if we can proceed with having the actual interview with the NL guys.

1. Can you rate you skill level in Merak Framework?
2. Are you familiar with Kingsroad?
3. How about Touchpoint API Architecture
4. How do you secure your application?
5. How do you Implement Authorization and Authentication in your current squad, and/or with your previous experience?
6. How do you ensure code quality?
7. How do manage vulnerabilities?


Problem-Solving

https://www.linkedin.com/pulse/java-coding-interview-questions-top-10-akcoding-5mw0c/

### 1. FizzBuzz Problem
Write a program that prints the numbers from 1 to 100. But for multiples of three, print “Fizz” instead of the number, and for the multiples of five, print “Buzz”. For numbers that are multiples of both three and five, print “FizzBuzz”.

Here’s the FizzBuzz problem solved in Java:

``` java
public class FizzBuzz {
    public static void main(String[] args) {
        for (int i = 1; i <= 100; i++) {
            if (i % 3 == 0 && i % 5 == 0) {
                System.out.println("FizzBuzz");
            } else if (i % 3 == 0) {
                System.out.println("Fizz");
            } else if (i % 5 == 0) {
                System.out.println("Buzz");
            } else {
                System.out.println(i);
            }
        }
    }
}
```

This Java program iterates through numbers from 1 to 100 and prints “Fizz” for multiples of 3, “Buzz” for multiples of 5, and “FizzBuzz” for numbers that are multiples of both 3 and 5. Otherwise, it prints the number itself.

## Anagram

/*
Problem Statement:

Write a Java program to determine if two given strings are anagrams of each other. 
An anagram is a word or phrase formed by rearranging the letters of a different word or phrase, 
typically using all the original letters exactly once.

For example:
- "listen" and "silent" are anagrams.
- "triangle" and "integral" are anagrams.
- "hello" and "world" are not anagrams.
- "Racecar" and "racecar" are anagrams.
- "Debit card" and "bad credit" are anagrams, ignoring spaces and case.

Your program should take two strings as input and return true if they are anagrams, and false otherwise.
*/

``` java
import java.util.Arrays;

public class AnagramChecker {

    public static boolean areAnagrams(String str1, String str2) {
        // Remove spaces and convert to lowercase for case-insensitive comparison
        String cleanedStr1 = str1.replaceAll("\\s", "").toLowerCase();
        String cleanedStr2 = str2.replaceAll("\\s", "").toLowerCase();

        // Check if the lengths are different, if so, they cannot be anagrams
        if (cleanedStr1.length() != cleanedStr2.length()) {
            return false;
        }

        // Convert strings to character arrays and sort them
        char[] charArray1 = cleanedStr1.toCharArray();
        char[] charArray2 = cleanedStr2.toCharArray();
        Arrays.sort(charArray1);
        Arrays.sort(charArray2);

        // Compare the sorted character arrays
        return Arrays.equals(charArray1, charArray2);
    }

    public static void main(String[] args) {
        String str1 = "listen";
        String str2 = "silent";
        System.out.println("\"" + str1 + "\" and \"" + str2 + "\" are anagrams: " + areAnagrams(str1, str2));

        str1 = "triangle";
        str2 = "integral";
        System.out.println("\"" + str1 + "\" and \"" + str2 + "\" are anagrams: " + areAnagrams(str1, str2));

        str1 = "hello";
        str2 = "world";
        System.out.println("\"" + str1 + "\" and \"" + str2 + "\" are anagrams: " + areAnagrams(str1, str2));

        str1 = "Racecar";
        str2 = "racecar";
        System.out.println("\"" + str1 + "\" and \"" + str2 + "\" are anagrams: " + areAnagrams(str1, str2));

        str1 = "Debit card";
        str2 = "bad credit";
        System.out.println("\"" + str1 + "\" and \"" + str2 + "\" are anagrams: " + areAnagrams(str1, str2));
    }
}
```

Explanation:

areAnagrams(String str1, String str2) Function:

Takes two strings (str1 and str2) as input.
Cleaning:
str1.replaceAll("\\s", "").toLowerCase(): Removes all whitespace characters (spaces, tabs, etc.) and converts the string to lowercase. This ensures that the comparison is case-insensitive and ignores spaces. The same is done for str2.
Length Check:
if (cleanedStr1.length() != cleanedStr2.length()): If the lengths of the cleaned strings are different, they cannot be anagrams, so it returns false.
Character Array Conversion and Sorting:
char[] charArray1 = cleanedStr1.toCharArray();: Converts the cleaned string str1 into a character array.
char[] charArray2 = cleanedStr2.toCharArray();: Converts the cleaned string str2 into a character array.
Arrays.sort(charArray1);: Sorts the characters in charArray1 in ascending order.
Arrays.sort(charArray2);: Sorts the characters in charArray2 in ascending order.
Comparison:
Arrays.equals(charArray1, charArray2);: Compares the sorted character arrays. If they are equal (meaning they have the same characters in the same quantities), it returns true; otherwise, it returns false.
main(String[] args) Function:

Provides example usage of the areAnagrams function with various test cases.
Prints the results to the console.


## Application Design
Alright, here's a senior Java developer interview question designed to elicit a system design discussion, focusing on ordering, payment, and receipt generation:

Question:

"Imagine we need to design and implement a system for a restaurant that allows customers to order items, pay for their orders, and generate a printable receipt. Considering this system needs to be scalable, maintainable, and robust, walk me through your design process.

Specifically, I'd like you to discuss:

High-Level System Architecture: How would you break down the system into logical components or services? What technologies and design patterns would you consider using?
Data Model: How would you model the core entities, like orders, items, payments, and receipts? What database technology would you choose and why?
Order Processing: Describe the flow of an order from creation to fulfillment. How would you handle concurrent orders?
Payment Processing: How would you integrate with a payment gateway? What security considerations would you keep in mind?
Receipt Generation and Printing: What strategies would you use for generating and printing receipts? How would you handle different receipt formats or printing devices?
Error Handling and Resilience: How would you handle potential failures or errors in the system? How would you ensure the system remains resilient?
Scalability and Performance: How would you design the system to handle a large volume of orders and payments? What performance optimizations would you consider?"
Why this question is effective:

Open-ended: It encourages the candidate to demonstrate their design thinking and problem-solving skills.
Comprehensive: It covers various aspects of application design, including architecture, data modeling, concurrency, security, and scalability.
Real-world scenario: It relates to a common and understandable business problem.
Depth of knowledge: It allows the interviewer to gauge the candidate's understanding of various technologies and design patterns.
Discussion prompt: Each point can lead to a deeper discussion about the candidate's experience and expertise.
Expected areas of discussion from the candidate:

Microservices or Monolithic application structure.
Relational or NoSQL databases.
RESTful APIs or Message queues for communication.
Design patterns like Command, Strategy, or Observer.
Payment gateway integration using APIs.
PDF generation libraries or templating engines for receipts.
Logging, monitoring, and alerting for error handling.
Load balancing, caching, and database indexing for performance.
How they would handle transaction management, and ensure data consistancy.
This question will give you a good understanding of how a senior Java developer approaches system design and their ability to translate requirements into a robust and scalable solution.

Question:

"Imagine we're building an e-commerce platform with these core functionalities: users can list items for sale, order items, process payments, and generate printable receipts. Describe how you would design this system, focusing on the architecture, key components, and how they interact. Specifically, I'd like to understand how you would handle the following:

Item Listing: How would you model and store item data? How would you handle searching and filtering?
Order Placement: How would you design the order processing flow, including inventory management?
Payment Processing: How would you integrate with a payment gateway? What are your considerations for security and reliability?
Receipt Generation: How would you generate and store receipts? How would you handle printing or exporting receipts?"
Expected Follow-up Prompts (to guide the conversation):

"Let's dive deeper into the database design. What kind of database would you choose and why?"
"How would you handle concurrency issues, especially during order placement and inventory updates?"
"What design patterns would you consider applying in this system, and where?"
"How would you ensure the system is scalable and maintainable?"
"How would you handle failure scenarios, such as payment gateway outages?"
"How would you test this system?"
"How would you secure sensitive data, such as payment information?"
"What kind of API's would you create for the different functions?"
What the Interviewer is Looking For:

Architectural Understanding: Ability to articulate a clear and logical system architecture (e.g., microservices, layered architecture).
Design Patterns: Knowledge and application of relevant design patterns (e.g., Strategy, Factory, Observer).
Database Design: Understanding of database principles and the ability to choose an appropriate database (relational or NoSQL).
API Design: Ability to design RESTful or other types of APIs.
Concurrency and Scalability: Knowledge of concurrency control and strategies for building scalable systems.
Error Handling and Resilience: Understanding of how to handle errors and build resilient systems.
Security: Awareness of security best practices, especially for payment processing.
Testing: Understanding of different testing methodologies (unit, integration, end-to-end).
Communication: Ability to clearly communicate their design decisions.
Practicality: ability to create a system that is not over engineered.
By asking this question, you'll gain insight into the candidate's ability to think critically about system design, apply their Java knowledge in a practical context, and communicate their ideas effectively.