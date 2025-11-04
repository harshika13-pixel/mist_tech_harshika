# Module 1: Hello Hackers

## Challenge 1: Intro to Commands

In this challenge, you will invoke your first command! When you type a command and hit enter, the command will be invoked, as so:

```sh
hacker@dojo:~$ whoami
hacker
hacker@dojo:~$
```
Here, the user executed the whoami command, which simply prints the username (hacker) to the terminal. When the command terminates, the shell once again displays the prompt, ready for the next command.

### Solution:

The  ```hello``` command is invoked to print the flag.

```sh
$ hello
```

### Flag: 

```
pwn.college{o6iYQxgWUWMcbv3g_oFF7iqi3ML.QX3YjM1wyMxAzNzEzW}
```

### New Learnings:

1. Commands in linux are case sensitive: hello is different from HELLO.
2. The $ at the end of the prompt signifies that hacker is not an administrative user. For the administrative user, the prompt signifies that by printing # instead of $.



# Challenge 2: Intro To Arguments

Let's try something more complicated: a command with arguments, which is what we call additional data passed to the command. When you type a line of text and hit enter, the shell actually parses your input into a command and its arguments. The first word is the command, and the subsequent words are arguments. Observe:

```sh
hacker@dojo:~$ echo Hello
Hello
hacker@dojo:~$
```

In this case, the command was echo, and the argument was Hello. echo is a simple command that "echoes" all of its arguments back out onto the terminal, like you see in the session above.

Let's look at echo with multiple arguments:

```sh
hacker@dojo:~$ echo Hello Hackers!
Hello Hackers!
hacker@dojo:~$
```

In this case, the command was echo, and Hello and Hackers! were the two arguments to echo.

## Solution:

Invoking ```hello``` command with argument ```hackers```

```sh
$ hello hackers
```

## Flag: 

```
pwn.college{o6iYQxgWUWMcbv3g_oFF7iqi3ML.QX3YjM1wyMxAzNzEzW}
```

### New Learnings:

1. When a line of text is entered, the input is divided into a command and its arguments. The first word is the command, and the subsequent words are arguments.
2. echo is a simple command that "echoes" (repeats) all of its arguments back out onto the terminal.



# Challenge 3: Command History

You're going to type a lot of commands, and typing everything from scratch can be annoying. Luckily, the shell saves a history of every command you invoke.

You can scroll through those saved commands with the up/down arrow keys. In other challenges, the history will contain the log of the commands you've run, so if you need to run a similar command again, you can use the arrow keys to scroll through and find it.

## Solution:

The up arrows are used to navigate to the flag that has already been generated. 

## Flag: 

```
pwn.college{o6iYQxgWUWMcbv3g_oFF7iqi3ML.QX3YjM1wyMxAzNzEzW}
```
 
### New Learnings:

This feature makes our job less strenuous by helping us navigating through the previously used commands by the up and down arrow keys. It is very useful in challenges where similar commands are to be repeated.