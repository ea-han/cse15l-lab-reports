# Lab Report 3: Researching Commands
**This lab is about researching the find command. We will explore different ways to use the find command.**

The find command in Linux can be modified with various options, or flags, to change its behavior. Here are some commonly used modifiers for the find command:


## 1. -iname: Searches for files with a specific name, case-insensitively. For example, find / -iname example.txt will search for a file named "example.txt" or "Example.txt" in the root directory and all subdirectories.

This is useful when we don't know what case the file we are searching for is in. It is also useful when we are trying to find all files containing a phrase, regardless of case.

**Let's try this out. Here we are looking for a file called Bahamas-History.txt, but lets say we don't know if it is capitalized or not. By using iname, we can ignore capitalization:**

Here is the command:

```
$ find -iname bahamas-history.txt
```

And here is the output:

```
./written_2/travel_guides/berlitz2/Bahamas-History.txt

```


**Now lets try to search for multiple files, while ignoring case:**

Here is the command:

```
$ find -iname "athens*"
```

And here is the output:

```
./written_2/travel_guides/berlitz2/Athens-History.txt
./written_2/travel_guides/berlitz2/Athens-Intro.txt
./written_2/travel_guides/berlitz2/Athens-WhatToDo.txt
./written_2/travel_guides/berlitz2/Athens-WhereToGo.txt
```

## 2. -type: Specifies the type of file to be searched for. It can be set to f for a regular file, d for a directory, l for a symbolic link, or c for a character special file. For example, find / -type f will search for regular files in the root directory and all subdirectories.

This is useful when we are looking for a specific file type, or trying to narrow our search to only directories.

**Let's search specifically for directories by adding -type d:**

Here is the command:

```
$ find written_2/ -type d
```

And here is the output:

```
written_2/
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Castro
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Rybczynski
written_2/travel_guides
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz2
```

**Now lets look for regular files with -type f. This will exclude directories and only search for files:**

Here is the command:

```
$ find written_2/ -type f
```

And here is the output:

```
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch7.txt
written_2/non-fiction/OUP/Castro/chA.txt
written_2/non-fiction/OUP/Castro/chB.txt
...
```


## 3. -mtime: Searches for files that have been modified within a specified number of days. For example, find / -mtime -7 will search for files that have been modified in the last 7 days.

This command is useful when we are looking for files that have been recently modified, or collecting files that we have worked on to push to a repository.

**Since we have just cloned this repo, if I search for files that have been modified within the last day, It should return all files:**

Here is the command:

```
$ find written_2/ -mtime -1
```

And here is the output:

```
written_2/
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch7.txt
written_2/non-fiction/OUP/Castro
written_2/non-fiction/OUP/Castro/chA.txt
written_2/non-fiction/OUP/Castro/chB.txt
written_2/non-fiction/OUP/Castro/chC.txt
written_2/non-fiction/OUP/Castro/chL.txt
written_2/non-fiction/OUP/Castro/chM.txt
written_2/non-fiction/OUP/Castro/chN.txt
written_2/non-fiction/OUP/Castro/chO.txt
written_2/non-fiction/OUP/Castro/chP.txt
written_2/non-fiction/OUP/Castro/chQ.txt
written_2/non-fiction/OUP/Castro/chR.txt
written_2/non-fiction/OUP/Castro/chV.txt
written_2/non-fiction/OUP/Castro/chW.txt
written_2/non-fiction/OUP/Castro/chY.txt
written_2/non-fiction/OUP/Castro/chZ.txt
...
```

**If we do the same with an mtime of 0, we should get 0 files, since they were all modified within the last day:**

Here is the command:

```
$ find written_2/ -mtime -0
```

And here is the output:

```

```

## 4. -size: Searches for files with a specified size. For example, find / -size +100M will search for files larger than 100 MB in the root directory and all subdirectories.

This command is good for looking for specific file sizes. This is useful if we are searching for all .txt files in a collection of directories, or want only large files.

**Lets try to find all files LESS than 3KB. The - in -3k denotes less than:**

Here is the command:

```
$ find written_2/ -size -3k
```

And here is the output:

```
written_2/
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Castro
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Rybczynski
written_2/travel_guides
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRIbiza.txt
written_2/travel_guides/berlitz1/HandRIstanbul.txt
written_2/travel_guides/berlitz1/HandRJerusalem.txt
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt
written_2/travel_guides/berlitz1/HandRLasVegas.txt
written_2/travel_guides/berlitz1/HandRLisbon.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/HandRMadeira.txt
written_2/travel_guides/berlitz1/HandRMallorca.txt
written_2/travel_guides/berlitz2

```

**Now lets search for all files GREATER than 30KB. The + denotes greater than.**

Here is the command:

```
$ find written_2/ -size +30k
```

And here is the output:

```
written_2/
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Castro
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Rybczynski
written_2/travel_guides
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRIbiza.txt
written_2/travel_guides/berlitz1/HandRIstanbul.txt
written_2/travel_guides/berlitz1/HandRJerusalem.txt
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt
written_2/travel_guides/berlitz1/HandRLasVegas.txt
written_2/travel_guides/berlitz1/HandRLisbon.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/HandRMadeira.txt
written_2/travel_guides/berlitz1/HandRMallorca.txt
written_2/travel_guides/berlitz2

```


This lab report was written in part by ChatGPT.






