# Lab 4: Contest

**This is a step-by-step guide to the contest tasks.**


## 1. Setup Delete any existing forks of the repository you have on your account

![image](https://user-images.githubusercontent.com/110416337/221089733-046af582-228d-4e78-96c7-966a918ac2a2.png)


To delete the fork directory and all of the files it contains, we will use the following command:
```
rm -r lab7
```
This command removes all of the files in the directory and the directory itself. We can delete them all in one go using the -r modifier, denoting recursive action.

Keys Pressed:
```
rm -r lab7 <Enter>
```


## 2. Setup Fork the repository

**We will need to go onto github and create a fork. This is achieved by clicking the fork button on the main repo:**

![image](https://user-images.githubusercontent.com/110416337/221087668-cc25ab35-2bac-4e1f-911e-3d5724957183.png)

**Then, click Create Fork:**

 ![image](https://user-images.githubusercontent.com/110416337/221087877-c706c4ef-8a70-4d59-b26e-a29192bf17b8.png)
 
**Congrats! You just forked the repo.**

Keys Pressed:
```
<Left Mouse>, <Left Mouse>
```

We fork repositories when we want to a copy of a repository owned by someone else to your account. The primary purpose of forking is to allow users to work on a project without affecting the original source code.
 
## 3. The real deal Start the timer!

**Get a timer on hand and start it:**

![image](https://user-images.githubusercontent.com/110416337/221088184-18eedd6d-ae3c-4e43-a77f-1182a89acf3a.png)


## 4. Log into ieng6

![image](https://user-images.githubusercontent.com/110416337/221088551-c3089596-142f-4790-a249-07875e8f7094.png)

To log into ieng6 we can copy and paste the command from the week 1 page:https://ucsd-cse15l-w23.github.io/week/week1/ 
and replace the letters "zz" with our course-specific account letters from https://sdacs.ucsd.edu/~icc/index.php:

Keys Pressed:
```
<Ctrl+v><Left><Left><Left><Left><Left><Left><Left><Left><Left><Left><Left><Left><Left><Left><Left><Left><Backspace> a i h <Enter>,
[password] <Enter>
```

## 5. Clone your fork of the repository from your Github account

![image](https://user-images.githubusercontent.com/110416337/221380099-e57ad8dc-b390-445e-8ec1-68584a65980a.png)

We will use git clone to clone our lab7 fork. We can copy and paste the link of our repo into git with ctrl+v.

Keys Pressed:
```
git clone <Ctrl+v>
```
## 6. Run the tests, demonstrating that they fail

First, we must cd into the lab7 directory.

If we navigate to the week 3 CSE15L page, we can copy and paste the command ``javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`` to compile the java files.

Then, we can run them with  ``java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTester``, which is also from the week 3 page.

![image](https://user-images.githubusercontent.com/110416337/221385102-3b699bcf-2e04-4e89-b779-750ef8e3913f.png)
As you can see, one of the tests has failed.


Keys Pressed:
```
cd lab7 <Enter>,
<Ctrl+v> <Enter>,
<Ctrl+v> <Enter>
```
## 7. Edit the code file to fix the failing test

![image](https://user-images.githubusercontent.com/110416337/221385205-12e614c3-05ed-4c0a-9d7e-a20f9388e262.png)


Keys Pressed:
```
nano ListExamples.java <Enter>,

<Ctrl+w> result.add(0, s); <Enter>,
<left><left><left><left><left><left><left><left><left><left><left><left><left><left><Backspace><Backspace><Backspace>,

<Ctrl+w> result.add(list2.get(index2)); <Enter>,
<down><left><left><left><left><left><left><Backspace>1,
<Ctrl+o><Enter><Ctrl+x>
```
## 8. Run the tests, demonstrating that they now succeed

![image](https://user-images.githubusercontent.com/110416337/221385193-28c85908-7380-4bfb-8465-903e3a430db9.png)


Keys Pressed:
```

```
## 9. Commit and push the resulting change to your Github account

![image](https://user-images.githubusercontent.com/110416337/221385229-a3276e7f-b5f8-4a23-a2cf-0b8d9165be10.png)


Keys Pressed:
```
git add ListExamples.java <Enter>
git commit -m "init commit" <Enter>
git push <Enter>
```
