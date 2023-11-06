# EX.7-IMPLEMENTATION-OF-SYSTEM-CALLS-READ-WRITE-FORK-OPEN-CLOSE

## AIM:
C program using open, read, write, close , create , fork() system calls. ALGORITHM:

## THEORY :
O_RDONLY: read only, O_WRONLY: write only, O_RDWR: read and write, O_CREAT: create file if it doesn’t exist, O_EXCL: prevent creation if it already exists
close: Tells the operating system you are done with a file descriptor and Close the file which pointed by fd. Syntax: int close(int fd); fd :file descriptor

## ALGORITHM:
Start the program. Open a file for O_RDWR for R/W,O_CREATE for creating a file ,O_TRUNC for truncate a file. Using getchar(), read the character and stored in the string[] array. The string [] array is write into a file close it. Then the first is opened for read only mode and read the characters and displayed it and close the file. Use Fork(). Stop the program.

## PROGRAM:
```
#include<sys/stat.h> 
#include<stdio.h> 
#include<fcntl.h> 
#include<sys/types.h> 
int main() 
{ 
int n,i=0; 
int f1,f2; 
char c,strin[100]; 
f1=open("data",O_RDWR|O_CREAT|O_TRUNC); 
while((c=getchar())!='\n') 
{ 
strin[i++]=c; 
} 
strin[i]='\0'; 
write(f1,strin,i); 
close(f1); 
f2=open("data",O_RDONLY); 
read(f2,strin,0); 
printf("\n%s\n",strin); 
close(f2); 
fork(); 
return 0; 
}
```
## OUTPUT:
![image](https://github.com/Madhav005/EX.7-IMPLEMENTATION-OF-SYSTEM-CALLS-READ-WRITE-FORK-OPEN-CLOSE/assets/110885274/ba56d2e7-48df-4c56-85f5-e618e2978ba9)

## RESULT:
Thus, open, read, write, close , create , fork() system calls implemented successfully using c program.


