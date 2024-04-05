# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:
```
C Program to print process ID and parent Process ID using Linux API system calls
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
int main(void)
{	//variable to store calling function's process id
	pid_t process_id;
	//variable to store parent function's process id
	pid_t p_process_id;
	//getpid() - will return process id of calling function
	process_id = getpid();
	//getppid() - will return process id of parent function
	p_process_id = getppid();
	//printing the process ids

//printing the process ids
	printf("The process id: %d\n",process_id);
	printf("The process id of parent function: %d\n",p_process_id);
	return 0; }
,,,
##OUTPUT
![316412389-eee79ac8-23fb-4cb7-8b53-3b095d6cbc6d](https://github.com/shivanshyam79/Linux-Process-API-fork-wait-exec/assets/151513860/61fa7829-2a3a-4615-81de-0beecec7f42b)

## C Program to create new process using Linux API system calls fork() and exit()
```
#include <stdio.h>
#include<stdlib.h>
int main()
{ int pid; 
pid=fork(); 
if(pid == 0) 
{ printf("Iam child my pid is %d\n",getpid()); 
printf("My parent pid is:%d\n",getppid()); 
exit(0); } 
else{ 
printf("I am parent, my pid is %d\n",getpid()); 
sleep(100); 
exit(0);} 
}
,,,

##OUTPUT

## C Program to execute Linux system commands using Linux API system calls exec() family
```
#include <unistd.h>
#include <stdio.h>
#include <stdlib.h>
int main()
{
	printf("Running ps with execlp\n");
	execlp("ps", "ps", "ax", NULL);
	printf("Done.\n");
	exit(0);
}
,,,
##OUTPUT
![316740580-7c8740eb-ea50-477f-8aab-5db463399d0d](https://github.com/shivanshyam79/Linux-Process-API-fork-wait-exec/assets/151513860/40dbf4c6-aefa-460e-972b-f2334c2fbf54)

# RESULT:
The programs are executed successfully.
