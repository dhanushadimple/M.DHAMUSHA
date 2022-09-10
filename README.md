   EXPERIMENT 1:
                            Create a new process by invoking the appropriate system call. Get the process identifier of the currently running process and its respective parent using system calls and display the same using a C program

AIM: 
Create a new process by invoking the appropriate system call. Get the process identifier of the currently running process and its respective parent using system calls and display the same using a C program.
ALGORITHM:
Step 1 : Start program.
Step 2  : An existing process can create a new one by calling the fork() function.
Step 3 : The new process created by fork() is called the child process.
Step 4  : We are using her getpid()to get the process id.
Step 5 : Stop program..
PROGRAM:
#include<stdio.h>
#include<unistd.h>
int main()
{

  printf("Process ID: %d\n", getpid() );
  printf("Parent Process ID: %d\n", getppid() );

  return 0;
}

INPUT AND OUTPUT:
 
RESULT:
Thus the program has been successfully implemented using system call


    EXPERIMENT 2:
                     Identify the system calls to copy the content of one file to another and illustrate the same using a C program.

Aim:
 To identify the system calls to copy the content of one file to another and illustrate the same using a C program.
ALGORITHM:
Step 1 : Start program.
Step 2 :type the file name that file is readable
Step 3 : type the file name that the content should be copied in the other file 
Step 4 : the coping of the content is done
Step 5 : Stop program.
Program: 
#include <stdio.h>
#include <stdlib.h>
int main()
{
	FILE *fptr1, *fptr2;
	char filename[100], c;
	printf("Enter the filename to open for reading \n");
	scanf("%s", filename);
	fptr1 = fopen(filename, "r");
	if (fptr1 == NULL)
	{
		printf("Cannot open file %s \n", filename);
		exit(0);
	}
	printf("Enter the filename to open for writing \n");
	scanf("%s", filename);
	fptr2 = fopen(filename, "w");
	if (fptr2 == NULL)
	{
		printf("Cannot open file %s \n", filename);
		exit(0);
	}
	c = fgetc(fptr1);
	while (c != EOF)
	{
		fputc(c, fptr2);
		c = fgetc(fptr1);
	}
	printf("\nContents copied to %s", filename);
	fclose(fptr1);
	fclose(fptr2);
	return 0;
}


INPUT AND OUTPUT:
 
 
Result:  Thus the program copying one file to another has been successfully implemented using system calls.



   
EXPERIMENT 3:
                                Desig n a CPU scheduling program with C using First Come First Served technique with the following considerations. a. All processes are activated at time 0. b. Assume that no process waits on I/O devices.
AIM:
ToDesign a CPU scheduling program with C using First Come First Served technique with the following considerations. a. All processes are activated at time 0. b. Assume that no process waits on I/O devices.
AlGORITHM:
Step 1: start program
Step 2: Inside the structure declare the variables.
Step 3: Declare the variable i, j as integer, to time and to time is equal to zero.
Step 4: Get the value of „n‟ assign pid as I and  get the value of p[i].b time.
Step 5: Assign p[0] wtime as zero and tot time as btime and inside the loop calculate wait time and turnaround time.
Step 6: Calculate total wait time and total turnaround time by dividing by total number of process. Step 7: Print total wait time and total turnaround time.
Step 8: Stop the program
PROGRAM:
#include<stdio.h>
void main()
{
int n,bt[20],wt[20],tat[20],i,j; float avwt=0,avtat=0;printf("Enter total number of processes(maximum 20):");scanf("%d",&n);
printf("\nEnter Process Burst Time\n");for(i=0;i<n;i++)
{
printf("P[%d]:",i+1);
scanf("%d",&bt[i]);
} wt[0]=0;
for(i=1;i<n;i++)
{ wt[i]=0;for(j=0;j<i;j++)
wt[i]+=bt[j];
}
printf("\nProcess\t\tBurst Time\tWaiting Time\tTurnaround Time"); for(i=0;i<n;i++)
{
tat[i]=bt[i]+wt[i]; avwt+=wt[i]; avtat+=tat[i];printf("\nP[%d]\t\t%d\t\t%d\t\t%d",i+1,bt[i],wt[i],tat[i]);
} avwt/=i; avtat/=i;printf("\n\nAverage Waiting Time:%.2f",avwt);
printf("\nAverage Turnaround Time:%.2f",avtat);
}
INPUT AND OUTPUT:
 
RESULT:
Thus the program of cpu scheduling by using “frist come first serve”technique is implemented successfully..





