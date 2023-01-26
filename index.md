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

1. Underlined in orange is our string for storing what will be displayed on the main page. 
   When an add-message query is recieved, whatever is passed will be concatenated to this string.
2. Underlined in green is our URI object. The difference between a URI and a URL is that a 
   "URI identifies a resource and differentiates it from others by using a name, location, or both. 
   URL identifies the web address or location of a unique resource."
3. Circled in red is 
   






