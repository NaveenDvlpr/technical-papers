# CLI
**Kernel:** A kernel is the core of the operating system. It manages both hardware and software of the system. We can interact with kernel using system calls.

**Shell:** A user program that tranforms human readable commands to machine understandable(kernel) instructions.

**CLI**: An interface where we can provide commands and use utilities using the shell(Terminal).

Find all shells in the system.
```bash
cat etc/shells
```
Current shell name
```bash
echo $SHELL
```
Current shell ID
```bash
echo $$
```

### Filters
A filter is an utility which takes the input, transform and gives the output.
Ex: sort, uniq, grep etc.

### Pipes (|)
Pipes are used to pass input of one command to another command
```bash
cat book.txt | sort | uniq
```
We can use pipes to execute complex queries by piping the commands to one another.

### grep
The "grep" command is used to search a pattern in the input file or stream.
#### import grep flags
-i --> case insensitive  
-o --> only word  
-E --> extend regular expression  
-v --> invert match  
-n --> display the line numbers  
-w --> match whole words

### process
ps --> current process  
ps ef --> list all process  
pstree -p --> process tree with ids  
pidof <process> --> process ids  
pgrep <process> --> parent process id  
kill -9 <pid>  --> Force terminate a process  
top --> Lists the the current process running in the system  

### Network and system
ip addr --> My ip address  
uname -a --> system details  
lspci --> lists the PCI components  
lsusb --> lists the USB components  
ping --> To check the connecticity  
ss --> socket statistis  
curl --> To fetch data from the internet  

### Navigation
ctrl+r --> To generate previous commands  
tab --> Auto completion of command
down arrow --> previous command
up arrow --> next command

#### Few important points
\> --> Insert data  
\>> --> Append data  
ctrl+c(SIGINT) --> terminate an ongoing process  
ctrl+z(SIGABRT) --> suspend an ongoing process  
nano --> Text editor in the terminal
