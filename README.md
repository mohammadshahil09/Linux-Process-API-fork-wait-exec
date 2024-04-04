# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
## Name: guntur shaik mohammad shahil
## Reg.No: 212223240044
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

## C Program to print process ID and parent Process ID using Linux API system calls







## C Program to execute Linux system commands using Linux API system calls exec() family
```
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
 ```











##OUTPUT
![319534174-6ad35127-48f3-499b-be53-77d9a065b218](https://github.com/mohammadshahil09/Linux-Process-API-fork-wait-exec/assets/145742840/b86c9dfd-3e0a-4447-956f-9bf7b57a7d2c)










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
```












##OUTPUT
![318166120-6931ddaf-2e5d-4eff-8ec9-3d6ad65b3ea0](https://github.com/mohammadshahil09/Linux-Process-API-fork-wait-exec/assets/145742840/f94189b9-cc16-460e-930d-d126dd543514)










## C Program to execute Linux system commands using Linux API system calls exec() family
```
#include <stdlib.h>
#include <sys/wait.h>
#include <sys/types.h>
int main()
{       int status;
        printf("Running ps with execlp\n");
        execl("ps", "ps", "ax", NULL);
        wait(&status);
        if (WIFEXITED(status))
                printf("child exited with status of %d\n", WEXITSTATUS(status));
        else
                puts("child did not exit successfully\n");
        printf("Done.\n");
printf("Running ps with execlp. Now with path specified\n");
        execl("/bin/ps", "ps", "ax", NULL);
        wait(&status);
        if (WIFEXITED(status))
                printf("child exited with status of %d\n", WEXITSTATUS(status));
        else
                puts("child did not exit successfully\n");
        printf("Done.\n");
        exit(0);}
```
##OUTPUT
![318166238-33bec6e8-9091-4a0a-a14a-b0b02a8c6c0b](https://github.com/mohammadshahil09/Linux-Process-API-fork-wait-exec/assets/145742840/21db831f-f531-457e-a63f-d337b1acab93)



















# RESULT:
The programs are executed successfully.
