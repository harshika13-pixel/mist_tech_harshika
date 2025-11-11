
## Challenge 1: Learning from documentation

Welcome to the documentation for /challenge/challenge! To properly run this program, you will need to pass it the argument of --giveflag.

### Solution:

The ```/challenge/challenge --giveflag``` command is invoked to prints the flag.

```sh
$ /challenge/challenge --giveflag
```

### Flag: 

```
pwn.college{UXLfAvGp4W69CPhqXiN8Dmq7G4r.QX0ITO0wyMxAzNzEzW}
```

### New Learnings:

This challenge helps to dig into the concept of reading documentation.



## Challenge 2: Learning complex usage

Welcome to the documentation for /challenge/challenge! This program allows you to print arbitrary files to the terminal, when given the --printfile argument. The argument to the --printfile argument is the path of the flag to read. For example, /challenge/challenge --printfile /challenge/DESCRIPTION.md will print out the description of the level.

### Solution:

The ``` /challenge/challenge --printfile /flag``` command is invoked to prints the flag.

```sh
$ /challenge/challenge --printfile /flag
```

### Flag: 

```
pwn.college{0f9XT4molNyPmW_Lg1KWy8wv7zm.QX1ITO0wyMxAzNzEzW}
```

### New Learnings:

There are commands that take arguments to their arguments. For instance, find has a -name argument, and the -name argument itself takes an argument specifying the name to search for.



## Challenge 3: Reading manuals

The challenge in this level has a secret option that, when you use it, will cause the challenge to print the flag. You must learn this option through the man page for challenge. 

### Solution:

The ```man challenge``` command is invoked, which displays the manual. After reading, the "q" button is hit to close the manual. According to the manual's information, the `/challenge/challenge --gmmunf 100` is invoked to generate the flag.

```sh
$ man challenge
$ /challenge/challenge --gmmunf 100
```

### Flag: 

```
pwn.college{UgQO1mOmXEun_fMtBRraAAYOFay.QX0EDO0wyMxAzNzEzW}
```

### New Learnings:

1. man is short for manual, and will display (if available) the manual of the command you pass as an argument.
2. You can scroll around the manpage with your arrow keys and PgUp/PgDn. When you're done reading the manpage, you can hit q to quit.
3. Manpages are stored in a centralized database. This database lives in the /usr/share/man directory
4. The arguments to the man command aren't file paths, but just the names of the entries themselves (e.g., you run man yes to look up the yes manpage, rather than man /usr/bin/yes, which would be the actual path to the yes program but would result in man displaying garbage).



## Challenge 4: Searching Manuals

You can scroll man pages with the arrow keys (and PgUp/PgDn) and search with /. After searching, you can hit n to go to the next result and N to go to the previous result. Instead of /, you can use ? to search backwards!

Find the option that will give you the flag by reading the challenge man page.

### Solution:

The manual is opened by invoking the `man challenge` command. The `/flag` command helps to find the particular argument. The ```/challenge/challenge --ztntto``` is invoked, which displays the flag.

### Flag: 

```
pwn.college{4GKgA2kUL5QPJuwj0lTDVrcJtRF.QX1EDO0wyMxAzNzEzW}
```

### New Learnings:

1. We can scroll man pages with the arrow keys (and PgUp/PgDn) and search with /. 
2. After searching, we can hit n to go to the next result and N to go to the previous result. 
3. Instead of /, we can use ? to search backwards.



## Challenge 5: Searching For Manuals

This level is tricky: it hides the manpage for the challenge by randomizing its name. To figure out how to search for the right manpage, read the man page manpage by doing: `man man`.

HINT 1: man man teaches you advanced usage of the man command itself, and you must use this knowledge to figure out how to search for the hidden manpage that will tell you how to use `/challenge/challenge`

HINT 2: though the manpage is randomly named, you still actually use `/challenge/challenge` to get the flag!

### Solution:

hacker@man~searching-for-manuals:~$ `man man`
hacker@man~searching-for-manuals:~$ `man -k /challenge/challenge` 
wwawvuisoz (1)       - print the flag!

hacker@man~searching-for-manuals:~$ `man -K /challenge/challenge`
hacker@man~searching-for-manuals:~$ `/challenge/challenge --wwawvu 425`

Here, the manual shows various commands which we try to find the secret code. 

### Flag: 

```
pwn.college{42wwNEPawN5vNLu0iKsozMHAHGI.QX2EDO0wyMxAzNzEzW}
```

### New Learnings:

`man man` teaches you advanced usage of the man command itself. 



## Challenge 6: Helpful Programs

Some programs don't have a man page, but might tell you how to run them if invoked with a special argument. Usually, this argument is --help, but it can often be -h or, in rare cases, -?, help, or other esoteric values like /? (though that latter is more frequently encountered on Windows).

In this level, you will practice reading a program's documentation with --help.

### Solution:

The ```/challenge/challenge --help``` is invoked, which displays the following:

usage: a challenge to make you ask for help [-h] [--fortune]
                                            [-v]
                                            [-g GIVE_THE_FLAG]
                                            [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct
                        value
  -p, --print-value     print the value that will cause the -g
                        option to give you the flag

Next, the `/challenge/challenge --p` is invoked, which displays:
The secret value is: 230

The final command which displays the flag is:
`/challenge/challenge --g 230`

### Flag: 

```
pwn.college{ADQEvPhL2URiKblgKJspvQYKJvq.QX3IDO0wyMxAzNzEzW}
```

### New Learnings:

Some programs don't have a man page, but might tell you how to run them if invoked with a special argument. Usually, this argument is --help, but it can often be -h or, in rare cases, -?, help, or other esoteric values like /?



## Challenge 7: Help for Builtins

In this challenge, we'll practice using `help` to look up help for builtins. This challenge's `challenge` command is a shell builtin, rather than a program. Lookup its help to figure out the secret value to pass to it.

### Solution:

The ```help challenge``` command is invoked, which displays the following:
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "44XwiBg1".  

The `challenge --secret 44XwiBg1` is invoked to generate the flag.


### Flag: 

```
pwn.college{44XwiBg1jONf898PHKwu7wHjCb8.QX0ETO0wyMxAzNzEzW}
```

### New Learnings:

1. Some commands, rather than being programs with man pages and help options, are built into the shell itself. These are called builtins.
2. Builtins are invoked just like commands, but the shell handles them internally instead of launching other programs.
3. You can get a list of shell builtins by running the builtin help. You can get help on a specific one by passing it to the help builtin. 