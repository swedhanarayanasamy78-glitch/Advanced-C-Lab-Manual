EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER Aim: To write a C program to create a function to find the greatest number

Algorithm:

Include the necessary header #include <stdio.h>.
Use a series of if and else if statements to compare the values and return the maximum among them.
Declare variables n1, n2, n3, n4, and greater to store user input and the result.
Use scanf to take four integers as input.
Call the max_of_four function with the input integers and store the result in the greater variable
Program: #include <stdio.h>

int max_of_four(int a, int b, int c, int d) { int max = a;

if (b > max)
    max = b;

if (c > max)
    max = c;

if (d > max)
    max = d;

return max;
}

int main() { int n1, n2, n3, n4, greater;

printf("Enter four numbers: ");
scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

greater = max_of_four(n1, n2, n3, n4);

printf("Greatest number = %d", greater);

return 0;
}

Output: 
<img width="847" height="265" alt="image" src="https://github.com/user-attachments/assets/6eaead91-bae4-48a9-947b-0d60dba13f6c" />


Result: Thus, the program that create a function to find the greatest number is verified successfully.

EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND XOR COMPARISONS Aim: To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:

Define a function calculate_the_max that takes two integers n and k as parameters.
Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
Declare variables n and k to store user input.
Use scanf to take two integers as input.
Call the calculate_the_max function with input values.
Program:

#include <stdio.h>

void calculate_the_max(int n, int k) { int i, j; int a = 0, o = 0, x = 0; int value;

for (i = 1; i <= n; i++)
{
    for (j = i + 1; j <= n; j++)
    {
        value = i & j;

        if (value < k && value > a)
            a = value;

        value = i | j;

        if (value < k && value > o)
            o = value;

        value = i ^ j;

        if (value < k && value > x)
            x = value;
    }
}

printf("Maximum AND value = %d\n", a);
printf("Maximum OR value = %d\n", o);
printf("Maximum XOR value = %d\n", x);
}

int main() { int n, k;

printf("Enter n and k: ");
scanf("%d %d", &n, &k);

calculate_the_max(n, k);

return 0;
}

Output:
<img width="847" height="317" alt="image" src="https://github.com/user-attachments/assets/e52a6450-b470-4763-8c83-635cae19a051" />


Result: Thus, the program to print the maximum values for the AND, OR and XOR comparisons is verified successfully.

EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS Aim: To write a C program to write the logic for the requests

Algorithm:

Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
Use scanf to take two integers as input for the number of shelves and queries.
Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
Declare variables k and c to keep track of the book index and the total number of books.
Use a for loop to iterate over the queries.
Program:

#include <stdio.h>

int main() { int noshel, noque; int shelarr[100][100]; int nobookarr[100] = {0}; int type, x, y; int i;

printf("Enter number of shelves and queries: ");
scanf("%d %d", &noshel, &noque);

for (i = 0; i < noque; i++)
{
    printf("Enter query %d: ", i + 1);
    scanf("%d %d %d", &type, &x, &y);

    if (type == 1)
    {
        shelarr[x][nobookarr[x]] = y;
        nobookarr[x]++;
    }
    else if (type == 2)
    {
        printf("%d\n", shelarr[x][y]);
    }
    else if (type == 3)
    {
        printf("%d\n", nobookarr[x]);
    }
}

return 0;
}

Output: 
<img width="850" height="340" alt="image" src="https://github.com/user-attachments/assets/dda42b04-f811-4423-acfa-3b0d59d2551e" />


Result: Thus, the program to write the logic for the requests is verified successfully.

EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY. Aim: To write a C program print the sum of the integers in the array.

Algorithm:

Declare a variable n to store the number of integers.
Use scanf to take an integer n as input.
Declare an array a of size n to store the integers.
Declare a variable sum and initialize it to zero.
Use a for loop to iterate n times:
Use scanf to input each integer and add it to the sum.
Print the final sum using printf.
Program: #include <stdio.h>

int main() { int n, a[100]; int sum = 0; int i;

printf("Enter the number of elements: ");
scanf("%d", &n);

printf("Enter the elements:\n");

for (i = 0; i < n; i++)
{
    scanf("%d", &a[i]);
    sum = sum + a[i];
}

printf("Sum of the integers = %d", sum);

return 0;
}

Output:
<img width="840" height="395" alt="image" src="https://github.com/user-attachments/assets/0c10af9a-b7c7-46f7-a1f6-2531c50ef073" />


Result: Thus, the program prints the sum of the integers in the array is verified successfully.

EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE

Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

Input the sentence: Take a sentence from the user.
Initialize a counter variable: This will keep track of the number of words.
Process each character of the sentence: o Iterate through the sentence, checking each character. o If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
Display the result: After processing the sentence, output the total word count.
Program:

#include <stdio.h>

int main() { char sentence[200]; int count = 0; int inWord = 0; int i;

printf("Enter a sentence: ");
fgets(sentence, sizeof(sentence), stdin);

for (i = 0; sentence[i] != '\0'; i++)
{
    if (sentence[i] != ' ' &&
        sentence[i] != '\n' &&
        sentence[i] != '\t')
    {
        if (inWord == 0)
        {
            count++;
            inWord = 1;
        }
    }
    else
    {
        inWord = 0;
    }
}

printf("Number of words = %d", count);

return 0;
} Output:

<img width="856" height="237" alt="image" src="https://github.com/user-attachments/assets/229fa75e-baaa-4ae3-8c40-8bea4f1f3fbd" />

Result:

Thus, the program that counts the number of words in a given sentence is verified successfully.
