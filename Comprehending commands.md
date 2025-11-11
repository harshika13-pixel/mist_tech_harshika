
## Challenge 1: cat: not the pet, but the command!

The cat command is used to read files. cat will concatenate (hence the name) multiple files if provided multiple arguments. In this challenge, the flag has been copied to the flag file in the home directory (where your shell starts). Read it with cat.

### Solution:

The ``` cat flag``` command is invoked to prints the flag.

```sh
$ cat flag
```

### Flag: 

```
pwn.college{wvC1UXWLRadOffjYsnlbhhIcLdS.QXxcTN0wyMxAzNzEzW}
```

### New Learnings:

1. cat is most often used for reading out files.
2. cat will concatenate (hence the name) multiple files if provided multiple arguments. For example:
```sh
hacker@dojo:~$ cat myfile
This is my file!
hacker@dojo:~$ cat yourfile
This is your file!
hacker@dojo:~$ cat myfile yourfile
This is my file!
This is your file!
```
3. If no arguments are given at all, cat will read from the terminal input and output it.




## Challenge 2: catting absolute paths

Read the flag at its absolute path: /flag.

### Solution:

The ``` cat /flag``` command is invoked to prints the flag.

```sh
$ cat /flag
```

### Flag: 

```
pwn.college{sgfIvWZstd20-eE8twIewS5WJDQ.QX5ETO0wyMxAzNzEzW}
```

### New Learnings:

It is possible to cat(read) a file by specifying its absolute path.




## Challenge 3: more catting practice

The flag has been put in some crazy directory. But it is not allowed to change directories with cd, so no cat flag. The flag must be retrieved by absolute path, wherever it is.

### Solution:

The ```cat /usr/include/netrom/flag``` is invoked, which displays the flag. 

```sh
$ cat /usr/include/netrom/flag
```

### Flag: 

```
pwn.college{8Y_MmACfF3YEzBCbgfWRDCMktYe.QXwITO0wyMxAzNzEzW}
```



## Challenge 4: grepping for a needle in a haystack

There are a hundred thousand lines of text into the /challenge/data.txt file. grep it for the flag.

HINT: The flag always starts with the text pwn.college.

### Solution:

The ```grep pwn.college /challenge/data.txt``` is invoked, which displays the flag.

```sh
$ grep pwn.college /challenge/data.txt
```

### Flag: 

```
pwn.college{0hn_FQvKA8IAqIV0pqB6WHPxCa3.QX3EDO0wyMxAzNzEzW}
```

### New Learnings:

```hacker@dojo:~$ grep SEARCH_STRING /path/to/file```
Invoked like this, grep will search the file for lines of text containing SEARCH_STRING and print them to the console.




## Challenge 5: comparing files

There are two files in /challenge:

/challenge/decoys_only.txt contains 100 fake flags.
/challenge/decoys_and_real.txt contains all 100 fake flags plus the one real flag.
Use diff to find what's different between these files and get your flag.

### Solution:

The ```diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt``` is invoked, which displays the flag.
It also displays 34a35, which means that that after line 34 in the first file, the second file has an additional line, which is the required flag.

```sh
$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
```

### Flag: 

```
pwn.college{wO2YF6j5Tk8S6e6e-Y-dp5CPjdc.01MwMDOxwyMxAzNzEzW}
```

### New Learnings:

diff compares two files line by line and shows you exactly what's different between them. 

```sh
hacker@dojo:~$ cat file1
hello
world
hacker@dojo:~$ cat file2
hello
universe
hacker@dojo:~$ diff file1 file2
2c2
< world
---
> universe
```

The output tells us that line 2 changed (2c2), with world in the first file (<) being replaced by universe in the second file (>).

Similarly, if new lines are added, it would display something like 1a2, which means that after line 1 in the first file, the second file has an additional line (1a2 means "after line 1 of file1, add line 2 of file2").




## Challenge 6: listing files

In this challenge, /challenge/run has been renamed with some random name. List the files in /challenge to find it.

### Solution:

The `ls /challenge` command is invoked which lists the files in the directory challenge. The ```/challenge/16026-renamed-run-2896``` is invoked, which displays the flag.

```sh
$ ls /challenge
$ /challenge/16026-renamed-run-2896
```

### Flag: 

```
pwn.college{MP7-zutNw4MhOQ6chXU7RBoiTbG.QX4IDO0wyMxAzNzEzW}
```

### New Learnings:

ls will list files in all the directories provided to it as arguments, and in the current directory if no arguments are provided.




## Challenge 7: touching files

You can create a new, blank file by touching it with the touch command. Create two files: /tmp/pwn and /tmp/college, and run /challenge/run to get your flag.

### Solution:

The ```cd /tmp``` is invoked, which opens the tmp directory. Then the files pwn and college are created using touch command. then using ls command, we can check the files present in the tmp. The `/challenge/run` is invoked to generate the flag. 

```sh
$ cd /tmp
$ touch pwn
$ touch college
$ ls
$ /challenge/run
```

### Flag: 

```
pwn.college{cLUXqxR7jbZF8Hz3j0Jq5hHFB8V.QXwMDO0wyMxAzNzEzW}
```

### New Learnings:

You can create a new, blank file by touching it with the touch command.




## Challenge 8: removing files

This challenge will create a `delete_me` file in your home directory. Delete it, then run `/challenge/check`, which will make sure you've deleted it and then give you the flag.

### Solution:

The ```rm delete_me``` command is invoked, which deletes the delete_me file. The `/challenge/check` is invoked to generate the flag. 

```sh
$ rm delete_me
$ /challenge/check
```

### Flag: 

```
pwn.college{cz-RQslek4qiBBrBF8-kf5D5L_X.QX2kDM1wyMxAzNzEzW}
```

### New Learnings:

Files can be deleted with the rm command.




## Challenge 9: moving files

Move the `/flag` file into `/tmp/hack-the-planet`. When you're done, run `/challenge/check`, which will check things out and give the flag to you.

### Solution:

The ``` mv  /flag /tmp/hack-the-planet``` command is invoked, which moves the file flag. The `/challenge/check` is invoked to generate the flag. 

```sh
$  mv  /flag /tmp/hack-the-planet
$ /challenge/check
```

### Flag: 

```
pwn.college{gE6TMdMw_ihIOL5JgB4jzj4QYxj.0VOxEzNxwyMxAzNzEzW}
```

### New Learnings:

Files can be moved around with the mv command.



## Challenge 10: copying files

Copy the /flag file into /tmp/hack-the-planet (do it)! When you're done, run /challenge/check, which will check things out and give the flag to you.

### Solution:

The ``` cp  /flag /tmp/hack-the-planet``` command is invoked, which copies the file flag. The `/challenge/check` is invoked to generate the flag. 

```sh
$  cp  /flag /tmp/hack-the-planet
$ /challenge/check
```

### Flag: 

```
pwn.college{kS617aSGQgcLCW6tnmVsEBCvjoL.01NxQTMywyMxAzNzEzW}
```

### New Learnings:

Files can be copied with the cp command.




## Challenge 11: hidden files

`ls` doesn't list all the files by default. Linux has a convention where files that start with a `.` don't show up by default in ls and in a few other contexts. To view them with ls, you need to invoke ls with the `-a` flag. Find the flag, hidden as a dot-prepended file in /.

### Solution:

The ``` cd /``` command is invoked, which opens the / directory. The hidden files are displayed using the `ls -a` command. Then `cat .flag-17664995716713` is invoked to generate the flag. 

```sh
$  mv  /flag /tmp/hack-the-planet
$ /challenge/check
```

### Flag: 

```
pwn.college{ceS7GqajoqtfEvoa8GxqE8tbNx9.QXwUDO0wyMxAzNzEzW}
```

### New Learnings:

ls doesn't list all the files by default. To view them with ls, you need to invoke ls with the -a flag. 





## Challenge 12: An Epic Filesystem Quest

With your knowledge of cd, ls, and cat, find the hidden flag. Follow the clues to keep finding your path

### Solution:

The ``` cd /``` command is invoked, which opens the / directory. The files are displayed using the `ls` command. Then the clues have been followed. 

hacker@commands~an-epic-filesystem-quest:~$ `cd /`
hacker@commands~an-epic-filesystem-quest:/$ `ls`
BRIEF  challenge  flag  lib32   media  opt   run   sys  var
bin    dev        home  lib64   mnt    proc  sbin  tmp
boot   etc        lib   libx32  nix    root  srv   usr
hacker@commands~an-epic-filesystem-quest:/$ `cat flag`
cat: flag: Permission denied
hacker@commands~an-epic-filesystem-quest:/$ `cat BRIEF`
Yahaha, you found me!
The next clue is in: /usr/share/cmake-3.16/Help
hacker@commands~an-epic-filesystem-quest:/$ `cd /usr/share/cmake-3.16/Help`
hacker@commands~an-epic-filesystem-quest:/usr/share/cmake-3.16/Help$ `ls`
MESSAGE    generator  module      prop_gbl   prop_tgt
command    include    policy      prop_inst  release
cpack_gen  index.rst  prop_cache  prop_sf    variable
envvar     manual     prop_dir    prop_test
hacker@commands~an-epic-filesystem-quest:/usr/share/cmake-3.16/Help$ `cat MESSAGE`
Great sleuthing!
The next clue is in: /usr/share/racket/pkgs/at-exp-lib
hacker@commands~an-epic-filesystem-quest:/usr/share/cmake-3.16/Help$ `cd /usr/share/racket/pkgs/at-exp-lib`
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/at-exp-lib$ `ls`
INFO  LICENSE.txt  at-exp  info.rkt  scribble
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/at-exp-lib$ `cat INFO LICENSE.txt`
Congratulations, you found the clue!
The next clue is in: /usr/aarch64-linux-gnu/include/gnu

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
at-exp-lib

This package is distributed under the GNU Lesser General Public
License (LGPL).  This means that you can link this package into proprietary
applications, provided you follow the rules stated in the LGPL.  You
can also modify this package; if you distribute a modified version,
you must distribute it under the terms of the LGPL, which in
particular means that you must release the source code for the
modified software.  See http://www.gnu.org/copyleft/lesser.html
for more information.

hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/at-exp-lib$ `ls /usr/aarch64-linux-gnu/include/gnu`
BLUEPRINT-TRAPPED  lib-names.h     stubs-lp64.h
lib-names-lp64.h   libc-version.h  stubs.h
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/at-exp-lib$ `cat /usr/aarch64-linux-gnu/include/gnu/BLUEPRINT-TRAPPED`
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/drivers/net/wimax

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/at-exp-lib$ `cd /opt/linux/linux-5.4/drivers/net/wimax`
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/wimax$ `ls -a`
.  ..  .SECRET  Kconfig  Makefile  i2400m
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/wimax$ `cat .SECRET`
Congratulations, you found the clue!
The next clue is in: /usr/lib/python3/dist-packages/numpy/tests/__pycache__

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/wimax$ `cd /usr/lib/python3/dist-packages/numpy/tests/__pycache__`
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/numpy/tests/__pycache__$ `ls`
CUE
__init__.cpython-38.pyc
test_ctypeslib.cpython-38.pyc
test_matlib.cpython-38.pyc
test_numpy_version.cpython-38.pyc
test_public_api.cpython-38.pyc
test_reloading.cpython-38.pyc
test_scripts.cpython-38.pyc
test_warnings.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/numpy/tests/__pycache__$ `cat CUE`
Yahaha, you found me!
The next clue is in: /usr/local/lib/python3.8/dist-packages/selenium/webdriver/wpewebkit/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/numpy/tests/__pycache__$ `cd /usr/local/lib/python3.8/dist-packages/selenium/webdriver/wpewebkit/__pycache__`
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/selenium/webdriver/wpewebkit/__pycache__$ `ls`
TIP                      service.cpython-38.pyc
__init__.cpython-38.pyc  webdriver.cpython-38.pyc
options.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/selenium/webdriver/wpewebkit/__pycache__$ `cat TIP`
Lucky listing!
The next clue is in: /usr/share/man/hu/man8

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/selenium/webdriver/wpewebkit/__pycache__$ cd /usr/share/man/hu/man8
hacker@commands~an-epic-filesystem-quest:/usr/share/man/hu/man8$ `ls -a`
.  ..  .DISPATCH  lastlog.8.gz
hacker@commands~an-epic-filesystem-quest:/usr/share/man/hu/man8$ `cat .DISPATCH`
Lucky listing!
The next clue is in: /etc/ufw/applications.d/apache2
hacker@commands~an-epic-filesystem-quest:/usr/share/man/hu/man8$ `cd /etc/ufw/applications.d/apache2`
hacker@commands~an-epic-filesystem-quest:/etc/ufw/applications.d/apache2$ `ls`
WHISPER
hacker@commands~an-epic-filesystem-quest:/etc/ufw/applications.d/apache2$ `cat WHISPER`
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{gjjaE5OINoXsbwFDb-AMmOCTLkW.QX5IDO0wyMxAzNzEzW}

### Flag: 

```
pwn.college{gjjaE5OINoXsbwFDb-AMmOCTLkW.QX5IDO0wyMxAzNzEzW}
```




## Challenge 13: making directories

Create a /tmp/pwn directory and make a college file in it. Then run /challenge/run, which will check your solution and give you the flag.

### Solution: 

The `mkdir /tmp/pwn` is invoked to create a directory. Then it is opened using `cd /tmp/pwn`. Then the `touch college` command created a file. and finally, the `/challenge/run` command invokes the flag.

```sh
$ mkdir /tmp/pwn
$ cd /tmp/pwn
$ touch college
$ /challenge/run
```

### Flag: 

```
pwn.college{k-ftu_JhOvtDSAtI8Euj0_VwlW8.QXxMDO0wyMxAzNzEzW}
```

### New Learnings:

You make directories using the mkdir command.




## Challenge 14: finding files

The flag is hidden in a random directory on the filesystem. It's still called flag. Find it. 
First, there are other files named flag on the filesystem. Don't panic if the first one you try doesn't have the actual flag in it. Second, there're plenty of places in the filesystem that are not accessible to a normal user. These will cause find to generate errors, but you can ignore those.

## Solution: 

`find / -name flag` is invoked which generates all files with "flag". Then we use `cat` to check each of the files which are generated. 

hacker@commands~finding-files:~$ `find / -name flag`
find: ‘/root’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
find: ‘/tmp/tmp.4mK6TfTSUV’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/share/racket/pkgs/redex-pict-lib/redex/compiled/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ `cat /usr/local/lib/python3.8/dist-packages/pwnlib/flag`
cat: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ cat `/usr/share/racket/pkgs/redex-pict-lib/redex/compiled/flag`
pwn.college{IK8Olqc1Khe1kLZex06wpap7k9J.QXyMDO0wyMxAzNzEzW}

### Flag: 

```
pwn.college{IK8Olqc1Khe1kLZex06wpap7k9J.QXyMDO0wyMxAzNzEzW}
```

### New Learnings:

1. The find command takes optional arguments describing the search criteria and the search location.
        If you don't specify a search criteria, find matches every file.
        If you don't specify a search location, find uses the current working directory (.).
2. When working with find, we need to be patient because it can take time.




## Challenge 15: linking files

In this level the flag is, as always, in /flag, but /challenge/catflag will instead read out /home/hacker/not-the-flag. Use the symlink, and fool it into giving you the flag.

### Solution:

```sh
$ ln -s /flag /home/hacker/not-the-flag
$ /challenge/catflag
```

### Flag: 

```
pwn.college{IS9Eyp8KL3ZXFwo9-sFDyQgv8Er.QX5ETN1wyMxAzNzEzW}
```

### New Learnings:

1. Links come in two flavors: hard and soft (also known as symbolic) links:

        A hard link is when you address your apartment using multiple addresses that all lead directly to the same place (e.g., Apt 2 vs Unit 2).
        A soft link is when you move apartments and have the postal service automatically forward your mail from your old place to your new place.

2. Symbolic links are created with the ln command with the -s argument. When you access the symbolic link, Linux will realize that it is a symbolic link, read the original file name, and then (typically) automatically access that file.