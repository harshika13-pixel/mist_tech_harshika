# Module 2: Pondering Paths

## Challenge 1: The Root

Start the challenge, launch a terminal, invoke the pwn program using its absolute path, and Capture that Flag!

### Solution:

The ``` /pwn``` command is invoked to print the flag.

```sh
$ /pwn
```

### Flag: 

```
pwn.college{gFelGljeKL5xr_AbqUi_IKbeT4M.QX4cTO0wyMxAzNzEzW}
```

### New Learnings:

1. The filesystem starts at /. Under that, there are a whole mess of other directories, configuration files, programs, and flags.
2. You can invoke a program by providing its path on the command line.
3. In this case, the the exact path is entered, starting from /, so the path would be /pwn. This style of path, one that starts with the root directory, is referred to as an "absolute path".



## Challenge 2: Programs and absolute paths

This is a slightly more complicated path! Except for in the previous level, challenges in pwn.college are in the challenge directory and the challenge directory is, in turn, right in the root directory (/). The path to the challenge directory is, thus, /challenge. The name of the challenge program in this level is run, and it lives in the /challenge directory. Thus, the path to the run challenge program is /challenge/run.

This challenge again requires you to execute it by invoking its absolute path. You'll want to execute the run file that is in the challenge directory that is, in turn, in the / directory. If you invoke the challenge correctly, it will give you the flag.

### Solution:

The ``` /challenge/run``` command is invoked to print the flag.

```sh
$ /challenge/run
```

### Flag: 

```
pwn.college{A3U7D1O487AJN_WuiKKL8BlbaWn.QX1QTN0wyMxAzNzEzW}
```

### New Learnings:

1. Here the "run" file is invoked which is in the "challenge" directory.  


## Challenge 3: Position thy self

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program.

### Solution:

The ``` /challenge/run``` command is invoked. Then the directory in which it is located is displayed, which is /var. Then, the directory is changed using ```cd /var```. Then the ``` /challenge/run``` is invoked again, which displays the flag. 

```sh
$ /challenge/run
$ cd /var
$ /challenge/run
```

### Flag: 

```
pwn.college{U2azESIJk2eVOEDn0l26GttqR6t.QX2QTN0wyMxAzNzEzW}
```

### New Learnings:

1. The cd command is used to change directory.
2. Each process has a directory in which it's currently hanging out.
3. The ~  shows the current path that your shell is located at.



## Challenge 4: Position elsewhere

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program.

### Solution:

The ``` /challenge/run``` command is invoked. Then the directory in which it is located is displayed, which is /proc/131/fd. Then, the directory is changed using ```cd /proc/131/fd```. Then the ``` /challenge/run``` is invoked again, which displays the flag. 

```sh
$ /challenge/run
$ cd /proc/131/fd
$ /challenge/run
```

### Flag: 

```
pwn.college{Ar-Dzq4gyKSoVHgn1iSFNIYU4XB.QX3QTN0wyMxAzNzEzW}
```

### New Learnings:

1. The cd command is used to change directory.
2. Each process has a directory in which it's currently hanging out.
3. The ~  shows the current path that your shell is located at.



## Challenge 5: Position yet elsewhere

This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program.

### Solution:

The ``` /challenge/run``` command is invoked. Then the directory in which it is located is displayed, which is /usr/share/doc/fontconfig. Then, the directory is changed using ```cd /usr/share/doc/fontconfig```. Then the ``` /challenge/run``` is invoked again, which displays the flag. 

```sh
$ /challenge/run
$ cd /usr/share/doc/fontconfig
$ /challenge/run
```

### Flag: 

```
pwn.college{UMhuBUiv4bHOYCkE-vY2L_uU68p.QX4QTN0wyMxAzNzEzW}
```

### New Learnings:

1. The cd command is used to change directory.
2. Each process has a directory in which it's currently hanging out.
3. The ~  shows the current path that your shell is located at.



## Challenge 6: implicit relative paths, from /

You'll need to run /challenge/run using a relative path while having a current working directory of /. Hint: your relative path starts with the letter c. 

### Solution:

The ``` cd /``` command is invoked. Thus the directory is changed to /. Then the ``` challenge/run``` command is invoked , which displays the flag. 

```sh
$ cd /
$ /challenge/run
```

### Flag: 

```
pwn.college{07k0IskBaH6zH75Wdeh6hD-LkCk.QX5QTN0wyMxAzNzEzW}
```

### New Learnings:

1. The cwd (Current Working Directory) is the directory that your prompt is currently located at.
2. The cwd is used to intrepret relative paths, as opposed to absolute paths (where the cwd does not matter). 
3. A relative path is any path that does not start at root (it does not start with /).



## Challenge 7: explicit relative paths, from /

This challenge will get you using . in your relative paths. Every directory has two implicit entries that you can reference in paths: . and .. . The first, ., refers right to the same directory. 

 The first, ., refers right to the same directory, so the following absolute paths are all identical to each other:

/challenge
/challenge/.
/challenge/./././././././././
/./././challenge/././

### Solution:

The ``` /challenge/run``` command is invoked. This is incorrect since we're not in the / directory. Then the ```cd /``` is invoked. The directory is changed to /. Then the ``` ./challenge/run``` command is invoked (explictly), which displays the flag. 

```sh
$ /challenge/run
$ cd /
$ ./challenge/run
```

### Flag: 

```
pwn.college{8VKYR2nvbf__MCj18rub8ZLzbD4.QXwUTN0wyMxAzNzEzW}
```

### New Learnings:

1. . always refers to the cwd.
2. Writing ./challenge means: "Start from the current directory (.), then go inside challenge"
3. Writing challenge alone (without ./) would also work, but using ./ makes it more explicit that its starting from cwd.


## Challenge 8: implicit relative path

Linux explicitly avoids automatically looking in the current directory when you provide a "naked" path. This is actually a safety measure: if Linux searched the current directory for programs every time you entered a naked path, you could accidentally execute programs in your current directory that happened to have the same names as core system utilities. 

This challenge requires you to explicitly use relative paths to launch run in this scenario. The way to do this is to tell Linux that you explicitly want to execute a program in the current directory, using . .

### Solution:

The ``` cd /challenge``` command is invoked. Thus the directory is changed to /challenge. Then the ```./run``` command is invoked , which displays the flag. 

```sh
$ cd /challenge
$ ./run
```

### Flag: 

```
pwn.college{IBEmMZpxX2iiQ9oUCvuZOUuSwop.QXxUTN0wyMxAzNzEzW}
```

### New Learnings:

1. Even when the prompt is in the required directory(the file is in the cwd), we need to explicitly tell Linux (using .) that we want to execute the program in the cwd. 
2. If the path is naked, it will NOT invoke the required program, and will display an error: ```bash: run: command not found```.
3. This is a actually a safety measure, if Linux searched the current directory for programs every time you entered a naked path, you could accidentally execute programs in your current directory that happened to have the same names as core system utilities.



## Challenge 9: home sweet home

In this challenge, /challenge/run will write a copy of the flag to any file you specify as an argument on the commandline, with these constraints:

1.Your argument must be an absolute path.
2.The path must be inside your home directory.
3.Before expansion, your argument must be three characters or less.
Again, you must specify your path as an argument to /challenge/run as so:

```hacker@dojo:~$ /challenge/run YOUR_PATH_HERE```

### Solution:

The ``` /challenge/run ~/f``` command is invoked. This writes the file to /home/hacker/f, and displays the flag

```sh
$ cd /challenge
$ ./run
```

### Flag: 

```
pwn.college{k3euyzGeEcBFNGTQm6a337amAQp.QXzMDO0wyMxAzNzEzW}
```

### New Learnings:

1. Every user has a home directory, typically under /home in the filesystem. In the dojo, my home directory is /home/hacker. The home directory is typically where users store most of their personal files.
2. The ~ is the cwd, with ~ being short for /home/hacker.
3. Whenever bash sees ~ provided as the start of an argument in a way consistent with a path, it will expand it to the home directory.
4. The expansion of ~ is an absolute path, and only the leading ~ is expanded. This means, for example, that ~/~ will be expanded to /home/hacker/~ rather than /home/hacker/home/hacker.
5. cd uses the home directory as the default destination.

