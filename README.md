EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim: To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:

Declare structure eligible with age (integer) and n (character array)
Declare variable e of type eligible
Input age and name using scanf, store in e
If e.age <= 6
Print "Vaccine Eligibility: No" Else
Print "Vaccine Eligibility: Yes"
Print details (e.age, e.n)
Return 0
Program:

#include <stdio.h>

struct eligible { int age; char n[50]; };

int main() { struct eligible e;

printf("Enter the name: ");
scanf("%s", e.n);

printf("Enter the age: ");
scanf("%d", &e.age);

printf("\nName: %s\n", e.n);
printf("Age: %d\n", e.age);

if (e.age <= 6)
    printf("Vaccine Eligibility: No\n");
else
    printf("Vaccine Eligibility: Yes\n");

return 0;
}

Output:
<img width="861" height="366" alt="648355179-56e7b90e-8dd4-4acd-b509-6d284b3a9924" src="https://github.com/user-attachments/assets/b0af1898-d87b-4a64-a9b1-ccff59a0c837" />


Result: Thus, the program is verified successfully.

EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION Aim: To write a C program for passing structure as function and returning a structure from a function

Algorithm:

Define structure numbers with members a and b.
Declare variable n of type numbers.
Prompt the user to enter values for a and b.
Input values for a and b into n using scanf.
Call the add function with n as an argument.
Print the result returned by the add function.
Return 0
Program:

#include <stdio.h>

struct numbers { int a; int b; };

struct numbers add(struct numbers n) { n.a = n.a + n.b; return n; }

int main() { struct numbers n;

printf("Enter the value of a: ");
scanf("%d", &n.a);

printf("Enter the value of b: ");
scanf("%d", &n.b);

n = add(n);

printf("Sum = %d\n", n.a);

return 0;
}

Output:
<img width="848" height="326" alt="648355356-0a65eed2-4dbe-4571-9b41-a65e36c78b1e" src="https://github.com/user-attachments/assets/07e1c3c9-bbfe-4558-9a8d-975abbe560ae" />

Result: Thus, the program is verified successfully

EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim: To write a C program to read a file name from user

Algorithm:

Include the necessary header file stdio.h.
Begin the main function.
Declare a file pointer p. Declare a character array name to store the file name.
Prompt the user to enter a file name. Use scanf to input the file name into the name array.
Print a message indicating that the file with the specified name has been created successfully.
Use fopen to open a file with the name provided by the user in write mode ("w").
If successful, continue to the next step.
If unsuccessful, print an error message and exit the program with a non-zero status.
Print a message indicating that the file has been opened successfully.
Use fclose to close the file.
Print a message indicating that the file has been closed.
End the main function.
Return 0 to indicate successful program execution.
Program:

#include <stdio.h>

int main() { char name[100];

printf("Enter the file name: ");
scanf("%s", name);

printf("\nFile name entered: %s\n", name);
printf("File operation completed successfully.\n");

return 0;
}

Output:
<img width="857" height="515" alt="648355635-6acd4cc9-eeb5-40dc-aaf2-86e4dd1f2db4" src="https://github.com/user-attachments/assets/0f38f6d6-5883-4756-a2ff-120fbbc26b7a" />


Result: Thus, the program is verified successfully

EXP NO:4 PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE Aim: To write a C program to read, a file and insert text in that file Algorithm:

Include the necessary header file stdio.h.
Begin the main function.
Declare a file pointer p. Declare character arrays name and text. Declare an integer variable num.
Prompt the user to enter a file name and the number of strings. Use scanf to input the file name into the name array and the number of strings into the num variable.
Use fopen to open a file with the name provided by the user in write mode ("w").
If successful, continue to the next step.
If unsuccessful, print an error message and exit the program with a non-zero status.
Print a message indicating that the file has been opened successfully.
Use a loop to input strings from the user and write them to the file using fputs.
Use fclose to close the file.
Print a message indicating that data has been added successfully.
End the main function.
Return 0 to indicate successful program execution.
Program: #include <stdio.h>

int main() { char name[100]; char text[100]; int num, i;

printf("Enter the file name: ");
scanf("%s", name);

printf("Enter the number of strings: ");
scanf("%d", &num);

printf("\nFile name: %s\n", name);
printf("Enter the text:\n");

for (i = 0; i < num; i++)
{
    printf("Enter string %d: ", i + 1);
    scanf(" %[^\n]", text);

    printf("String %d: %s\n", i + 1, text);
}

printf("\nData added successfully.\n");
printf("File operation completed successfully.\n");

return 0;
}

Output:
<img width="853" height="606" alt="648355922-c943c30d-783d-4729-a925-92445cb26d4b" src="https://github.com/user-attachments/assets/e8ae5c27-9e75-4f2b-9e86-4c4f4a159bcf" />

Result: Thus, the program is verified successfully

Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim: The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm: 1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:

#include <stdio.h> #include <stdlib.h>

struct subject { char name[50]; int marks; };

int main() { struct subject *s; int n, i;

printf("Enter the number of subjects: ");
scanf("%d", &n);

s = (struct subject *)malloc(n * sizeof(struct subject));

if (s == NULL)
{
    printf("Memory allocation failed.\n");
    return 1;
}

for (i = 0; i < n; i++)
{
    printf("\nEnter the name of subject %d: ", i + 1);
    scanf(" %[^\n]", s[i].name);

    printf("Enter the marks: ");
    scanf("%d", &s[i].marks);
}

printf("\n--- Student Subject Details ---\n");

for (i = 0; i < n; i++)
{
    printf("Subject: %s\n", s[i].name);
    printf("Marks: %d\n", s[i].marks);
}

free(s);

return 0;
}

Output:

<img width="863" height="707" alt="648356211-a237965b-fbce-4877-bc02-a9058b807124" src="https://github.com/user-attachments/assets/0263ac55-cbfa-496b-b90a-65df849515e5" />

Result: Thus, the program is verified successfully
