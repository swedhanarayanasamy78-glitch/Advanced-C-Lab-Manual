EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
#include <stdio.h>

#define MAX 5

int main() { int stack[MAX]; int top, i;<img width="857" height="567" alt="648381821-64385184-d47b-4b36-8b94-91230e806c45" src="https://github.com/user-attachments/assets/0dea050a-48c6-4c80-9aa6-9ca5f8e132de" />

printf("Enter the number of stack elements: ");
scanf("%d", &top);

if (top > MAX)
{
    printf("Stack size exceeded.");
    return 0;
}

printf("Enter the stack elements:\n");

for (i = 0; i < top; i++)
{
    scanf("%d", &stack[i]);
}

top = top - 1;

printf("\nStack elements are:\n");

for (i = top; i >= 0; i--)
{
    printf("%d\n", stack[i]);
}

return 0;
Output:

<img width="857" height="567" alt="image" src="https://github.com/user-attachments/assets/fe3f01fb-62e8-49f1-8cad-8ab352650330" />



Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
#include <stdio.h>

#define MAX 5

int main() { float stack[MAX]; int top = -1; float value; int i;

printf("Enter the element to push: ");
scanf("%f", &value);

if (top == MAX - 1)
{
    printf("Stack Overflow");
}
else
{
    top++;
    stack[top] = value;

    printf("\nElement %.2f pushed into stack.\n", value);

    printf("Stack elements are:\n");

    for (i = top; i >= 0; i--)
    {
        printf("%.2f\n", stack[i]);
    }
}

return 0;
}

Output:
<img width="857" height="392" alt="image" src="https://github.com/user-attachments/assets/071483db-ab49-4a51-99e1-f028891f9add" />





Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:

#include <stdio.h>

#define MAX 5

int main() { int queue[MAX]; int front = 0, rear, n, i;

printf("Enter the number of queue elements: ");
scanf("%d", &n);

if (n > MAX)
{
    printf("Queue size exceeded.");
    return 0;
}

rear = n - 1;

printf("Enter the queue elements:\n");

for (i = front; i <= rear; i++)
{
    scanf("%d", &queue[i]);
}

printf("\nQueue elements are:\n");

for (i = front; i <= rear; i++)
{
    printf("%d ", queue[i]);
}

return 0;
}
Output:
<img width="853" height="420" alt="image" src="https://github.com/user-attachments/assets/f96ddc43-eba4-4754-8fc7-0fbae8cc3335" />



Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

#include <stdio.h>

#define MAX 5

int main() { float queue[MAX]; int front = 0, rear = -1; float value; int i;

printf("Enter the element to insert: ");
scanf("%f", &value);

if (rear == MAX - 1)
{
    printf("Queue Overflow");
}
else
{
    rear++;
    queue[rear] = value;

    printf("\nElement %.2f inserted into queue.\n", value);

    printf("Queue elements are:\n");

    for (i = front; i <= rear; i++)
    {
        printf("%.2f ", queue[i]);
    }
}

return 0;
}
Output:
<img width="848" height="327" alt="image" src="https://github.com/user-attachments/assets/edb80213-3bcd-423d-bb8f-ecf20b41203a" />


Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:

#include <stdio.h>

#define MAX 5

int queue[MAX]; int front = 0; int rear = 3;

void deleteElement() { if (front == -1 || front > rear) { printf("Queue is empty.\n"); } else { printf("Deleted element: %d\n", queue[front]);

    front++;

    if (front > rear)
    {
        front = -1;
        rear = -1;
    }
}
}

int main() { int i;

queue[0] = 10;
queue[1] = 20;
queue[2] = 30;
queue[3] = 40;

printf("Queue elements before deletion:\n");

for (i = front; i <= rear; i++)
{
    printf("%d ", queue[i]);
}

printf("\n\n");

deleteElement();

printf("\nQueue elements after deletion:\n");

if (front == -1)
{
    printf("Queue is empty.");
}
else
{
    for (i = front; i <= rear; i++)
    {
        printf("%d ", queue[i]);
    }
}

return 0;
}
Output:
<img width="857" height="385" alt="image" src="https://github.com/user-attachments/assets/b096caef-29cb-4172-a256-0d8eb21b7c9f" />



Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
