# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

- `which` shows the location of the given command
- `man` displays the manual for the given command
- `type` describes how the given command would be interpreted. helpful for seeing what aliases are aliased to.
- `top` display Linux processes
- `ps` prints a snapshot of the current processes
- `cp` copy files
- `rm` remove files
- `mv` move or rename files
- `mkdir` make directory
- `rmdir` remove directory
- 'find' search for files
- `touch` changes the file timestamp to the current time
- `>` output to file
- `chmod` change mode bits, relates to user access permissions on files
- `chown` change file owner and group
- `echo` print the given input
- `cat` concatenate and print the given files
- `tail` output the last part of a file (use with -f to follow logs)
- `head` output the first of a file
- `less` view a file in a scrolling view
- `grep` print lines matching a pattern
- `|` pipe the output of the preceding command into the following command
- `curl` transfer a URL
- `expr` evaluate expression

---

### Q2.  List Files in Unix   

What do the following commands do:  
- `ls` list directory contents
- `ls -a` do not ignore entries starting with "."
- `ls -l` use a long listing format
- `ls -lh` use a long listing format with human readable sizes (e.g., 1K 234M 2G)
- `ls -lah` all of the above
- `ls -t` sort by modification time, newest first
- `ls -Glp` long list, don't print group names, append "/" indicator to directories

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

- `ls -R` list subdirectories recursively
- `ls -S` sort by file size, largest first
- `ls -u` order by access time
- `ls -m` display as comma separated list
- `ls -1` display each entry on a new line

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

`xargs` converts standard input into arguments for a given command. It's usually used with the pipe `|` symbol to use the output of one command as the arguments of another command, especially when the output of the first command is a long list of things like file names.

Example:

`grep` for occurrences of "numpy" in the markdown files of the current directory.

```
$ find . -name "*.md" | xargs grep "numpy"
./08-more_resources.md: * [Python NumPy Tutorial](http://cs231n.github.io/python-numpy-tutorial/)
./01a-install.md:import numpy
./README.md:Completing the pre-work is essential to obtaining the foundational knowledge necessary to succeed in the Metis data science bootcamp.  Each student should expect to spend **60+ hours of tutorials** to become familiar with software installation, editors, command line, Python (numpy, pandas, etc.), linear algebra and statistics.
```
