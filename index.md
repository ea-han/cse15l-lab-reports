# Lab Report 2: Servers and Bugs

**This tutorial will demonstrate the creation of a web server and some bug testing.**

# Part 1: Writing and Running a Web Server

---

**We will be writing a java class called StringServer. It will keep track of a single string and print it to the server. We will modify the strings with this request:**

``/add-message?s=<string>``

When we recieve this query, we will concatenate the argument after the "s=" to our server string.

This is what our code looks like:
![image](stringServer.png)

## Things to note:

1. Underlined in orange is our string for storing what will be displayed on the main page, "serverString". 
   When an add-message query is recieved, whatever is passed will be concatenated to this string.
2. Underlined in green is our URI object. The difference between a URI and a URL is that a 
   "URI identifies a resource and differentiates it from others by using a name, location, or both. 
   URL identifies the web address or location of a unique resource."
3. Our request handler is composed of two if statements. When it is called, we retrieve the path and 
   check if it is either "/" or "/add-message". 
   - Circled in red is the code for an empty string. This is where we display the stored string.
   - Circled in blue is the code for adding a string. These lines concatenate the entered string and a new line.
---
 **Here's a demonstration of how our server will function:**
 
First, we will start the server in the console using this command, where the numbers are the port number: ``java StringSearch 12101``
 
This is what we see in the console:
![image](https://user-images.githubusercontent.com/110416337/214997721-3c31b211-2d32-4a96-96e3-292cba58a3e0.png)
   
If we navigate to the link provided, this is what we see:
(note: the port is different because I took the screenshots at different times, but normally it would be the same.) 

 ![image](emptyPage.png)
 
 Lets add a string:
 
 ![image](firstMessage.png)
 
 Now lets see if it worked:
 
 ![image](firstMessageMainPage.png)
 
 Lets add another string:
 
 ![image](secondMessage.png)
 
 And navigate to the main page:
 
 ![image](secondMessageMainPage.png)
 
 
 
---

# Part 2: Bug Testing

**Here, I will demonstrate some basic JUnit testing and bugfixing.**

We will have two classes, ArrayExamples.java and ArrayTests.java. 

This is ArrayExamples, and it contains the method we will be testing:

```
  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

**Here is an input that will have the correct output:**
```
 int[] input1 = { 3 };
 ArrayExamples.reverseInPlace(input1);
 //input1 becomes { 3 }.
 ```

**In this case, the method functions as intended. Now lets look at an input that will cause errors.**

**The reason this occurs is because our method replaces 
``` 
// Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    int currInt;
    for (int i = 0; i < arr.length / 2; i += 1) {
      currInt = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = currInt;
    }
  }
  ```







