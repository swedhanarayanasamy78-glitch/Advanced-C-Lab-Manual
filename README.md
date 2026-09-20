EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER Aim: To write a C program print the lowercase English word corresponding to the number Algorithm:

Start
Initialize an integer variable n.
Input Validation
Switch Statement cases.
Case 5: Print "seventy one"
Case 6: Print "seventy two"
Case 13: Print "seventy three"
...
Case 13: Print "seventy nine"
Default: Print "Greater than 13"
Exit the program.
Program:

#include <stdio.h>

int main() { int n;

printf("Enter a number: ");
scanf("%d", &n);

switch(n)
{
    case 1:
        printf("one");
        break;
    case 2:
        printf("two");
        break;
    case 3:
        printf("three");
        break;
    case 4:
        printf("four");
        break;
    case 5:
        printf("five");
        break;
    case 6:
        printf("six");
        break;
    case 7:
        printf("seven");
        break;
    case 8:
        printf("eight");
        break;
    case 9:
        printf("nine");
        break;
    default:
        printf("Greater than 9");
}

return 0;
}

Output:
<img width="861" height="342" alt="648374487-b34c406c-fa76-40ae-a51f-06c7158b12fe" src="https://github.com/user-attachments/assets/efa89a18-a17d-4c8a-8196-8bd1f3462eb4" />
image
Result: Thus, the program is verified successfully

EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS IN A SINGLE LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 . Aim: To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3. Algorithm:

Start
Declare char array a[50] outer loop for each digit from 0 to 3
Initialize counter c to 0
For each character in the string print count c for current digit, followed by a space
Increment h to move to the next digit
End
Program:

#include <stdio.h>

int main() { char a[100]; int count[10] = {0}; int i;

printf("Enter the string: ");
scanf("%99s", a);

for(i = 0; a[i] != '\0'; i++)
{
    if(a[i] >= '0' && a[i] <= '9')
    {
        count[a[i] - '0']++;
    }
}

printf("Frequency of digits 0 to 9:\n");

for(i = 0; i < 10; i++)
{
    printf("%d ", count[i]);
}

return 0;
}

Output:
<img width="851" height="325" alt="648374681-4b3f239c-ada6-4997-8252-130a9c394e00" src="https://github.com/user-attachments/assets/fd42103d-6476-49b9-931c-d6cea549ce53" />

Result: Thus, the program is verified successfully 

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER. Aim: To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:

Start

Declare variables s (pointer to an array of strings) and n (number of strings)

Memory Allocation Dynamically allocate memory for s to store an array of strings

Input Read the number of strings n from the user Dynamically allocate memory for each string in s

Permutation Generation Loop

Memory Deallocation Free the memory allocated for each string in s Free the memory allocated for s

End

Program:

#include <stdio.h> #include <string.h>

void swap(char *a, char *b) { char temp = *a; *a = *b; *b = temp; }

void reverse(char s[], int start, int end) { while(start < end) { swap(&s[start], &s[end]); start++; end--; } }

int nextPermutation(char s[], int n) { int i, j;

i = n - 2;

while(i >= 0 && s[i] >= s[i + 1])
    i--;

if(i < 0)
    return 0;

j = n - 1;

while(s[j] <= s[i])
    j--;

swap(&s[i], &s[j]);

reverse(s, i + 1, n - 1);

return 1;
}

int main() { char s[100]; int n, i, j; char temp;

printf("Enter a string: ");
scanf("%99s", s);

n = strlen(s);

/* Sort the string */
for(i = 0; i < n - 1; i++)
{
    for(j = i + 1; j < n; j++)
    {
        if(s[i] > s[j])
        {
            temp = s[i];
            s[i] = s[j];
            s[j] = temp;
        }
    }
}

printf("Permutations in lexicographical order:\n");

do
{
    printf("%s\n", s);
}
while(nextPermutation(s, n));

return 0;
}

Output:

<img width="858" height="498" alt="648375034-c43e4d3f-4df6-42d6-9c69-bae8fcbcf2d7" src="https://github.com/user-attachments/assets/797e2377-9280-4701-90b2-110d817eba5a" />

Result: Thus, the program is verified successfully

EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS SHOWN BELOW. Aim: To write a C program to print a pattern of numbers from 1 to n as shown below. Algorithm:

Start
Declare integer variables n, i, j, min
Read the value of n from the user
Calculate the length of the side of the square matrix: len = n * 2 - 1
Matrix Generation Loop
Calculate min as the minimum distance to the borders
End
Program:

#include <stdio.h>

int main() { int n, i, j, len, min;

printf("Enter n: ");
scanf("%d", &n);

len = n * 2 - 1;

for(i = 0; i < len; i++)
{
    for(j = 0; j < len; j++)
    {
        min = i;

        if(j < min)
            min = j;

        if(len - 1 - i < min)
            min = len - 1 - i;

        if(len - 1 - j < min)
            min = len - 1 - j;

        printf("%d ", n - min);
    }

    printf("\n");
}

return 0;
}

Output:

<img width="852" height="465" alt="648375291-a3903320-b7a9-4eb5-8dfd-433806e0a782" src="https://github.com/user-attachments/assets/84d22592-6f85-4c0a-beb1-450207eed659" />

Result: Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

Start.
Define a function square() with no parameters. This function will return an integer value.
Inside the function: o Declare an integer variable to store the number. o Ask the user to input a number. o Calculate the square of the number (multiply the number by itself). o Return the squared value.
In the main function: o Call the square() function and display the result.
End.
Program:

#include <stdio.h>

int square() { int n;

printf("Enter a number: ");
scanf("%d", &n);

return n * n;
}

int main() { int result;

result = square();

printf("Square = %d", result);

return 0;
}

Output:

<img width="847" height="451" alt="648375519-37742ff9-f2f9-4331-aabf-3226155c2cc8" src="https://github.com/user-attachments/assets/5aa34996-1352-468b-81de-eb041974c1a3" />

Result: Thus, the program is verified successfully
