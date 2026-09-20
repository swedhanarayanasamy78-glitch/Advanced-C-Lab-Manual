EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST. Aim: To write a C program to display stack elements using linked list.

Algorithm:

Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
Declare a global variable head representing the starting node of the linked list.
Define a function display to print the elements of the linked list.
Declare a pointer p and initialize it with the head of the linked list.
Use a while loop to traverse the linked list:
Print the data of the current node.
Move to the next node using the next pointer.
Program:

#include <stdio.h> #include <stdlib.h>

struct Node { int data; struct Node *next; };

struct Node *head = NULL;

void display() { struct Node *p = head;

if (p == NULL)
{
    printf("Stack is empty.\n");
    return;
}

printf("Stack elements are:\n");

while (p != NULL)
{
    printf("%d\n", p->data);
    p = p->next;
}
}

int main() { struct Node *p1, *p2, *p3;

p1 = (struct Node *)malloc(sizeof(struct Node));
p2 = (struct Node *)malloc(sizeof(struct Node));
p3 = (struct Node *)malloc(sizeof(struct Node));

p1->data = 10;
p1->next = p2;

p2->data = 20;
p2->next = p3;

p3->data = 30;
p3->next = NULL;

head = p3;

display();

return 0;
}

Output:

<img width="851" height="258" alt="image" src="https://github.com/user-attachments/assets/54184f59-9a10-49ee-a443-255972842dd6" />

Result: Thus, the program to display stack elements using linked list is verified successfully.

EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST. Aim: To write a C program to pop an element from the given stack using liked list.

Algorithm:

Check for Empty Stack
If head is equal to NULL, Print "Stack is empty."
Else Proceed to the next step.
Set head to point to the next node in the stack.
Program:

#include <stdio.h> #include <stdlib.h>

struct Node { int data; struct Node *next; };

struct Node *head = NULL;

void push(int value) { struct Node *newNode;

newNode = (struct Node *)malloc(sizeof(struct Node));

newNode->data = value;
newNode->next = head;
head = newNode;
}

void pop() { struct Node *temp;

if (head == NULL)
{
    printf("Stack is empty.\n");
    return;
}

temp = head;

printf("Popped element: %d\n", head->data);

head = head->next;

free(temp);
}

void display() { struct Node *temp = head;

printf("Stack elements after pop:\n");

while (temp != NULL)
{
    printf("%d\n", temp->data);
    temp = temp->next;
}
}

int main() { push(10); push(20); push(30);

printf("Stack before pop:\n");
display();

printf("\n");

pop();

printf("\n");
display();

return 0;
}

Output:
<img width="847" height="482" alt="image" src="https://github.com/user-attachments/assets/940f444f-212f-40d1-bedc-bfa30af150b4" />


Result: Thus, the program to pop an element from the given stack using liked list is verified successfully.

EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST. Aim: To write a C program to display queue elements using linked list. Algorithm:

Check if Queue is Empty
Display Queue Elements
Print the data of the current node pointed to by front
Update front to point to the next node.
End the display function.
Program:

#include <stdio.h> #include <stdlib.h>

struct Node { int data; struct Node *next; };

struct Node *front = NULL; struct Node *rear = NULL;

void enqueue(int value) { struct Node *newNode;

newNode = (struct Node *)malloc(sizeof(struct Node));

newNode->data = value;
newNode->next = NULL;

if (front == NULL)
{
    front = newNode;
    rear = newNode;
}
else
{
    rear->next = newNode;
    rear = newNode;
}
}

void display() { struct Node *temp = front;

if (front == NULL)
{
    printf("Queue is empty.\n");
    return;
}

printf("Queue elements are:\n");

while (temp != NULL)
{
    printf("%d ", temp->data);
    temp = temp->next;
}
}

int main() { enqueue(10); enqueue(20); enqueue(30); enqueue(40);

display();

return 0;
}

Output:
<img width="855" height="301" alt="image" src="https://github.com/user-attachments/assets/6d3d962a-83c1-4ce5-807b-9055162df47d" />


Result: Thus, the program to display queue elements using linked list is verified successfully.

EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim: To write a C program to insert elements in queue using linked list

Algorithm:

Allocate Memory for New Node
Set Data and Next Pointer
Check if Queue is Empty
Set both front and rear to point to the new node p.
Set the next pointer of the current rear to point to the new node p.
End of Enqueue Operation
Program: #include <stdio.h> #include <stdlib.h>

struct Node { int data; struct Node *next; };

struct Node *front = NULL; struct Node *rear = NULL;

void enqueue(int value) { struct Node *p;

p = (struct Node *)malloc(sizeof(struct Node));

p->data = value;
p->next = NULL;

if (front == NULL)
{
    front = p;
    rear = p;
}
else
{
    rear->next = p;
    rear = p;
}
}

void display() { struct Node *temp = front;

while (temp != NULL)
{
    printf("%d ", temp->data);
    temp = temp->next;
}
}

int main() { int n, i, value;

printf("Enter the number of elements: ");
scanf("%d", &n);

for (i = 0; i < n; i++)
{
    printf("Enter element %d: ", i + 1);
    scanf("%d", &value);

    enqueue(value);
}

printf("\nQueue after insertion:\n");
display();

return 0;
}

Output:

<img width="855" height="387" alt="image" src="https://github.com/user-attachments/assets/bef4c649-3672-4b31-ac55-43393ad03fd2" />

Result: Thus, the program to insert elements in queue using linked list is verified successfully.

EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.

Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

Check if the queue is empty: o If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
Access the front element: o If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).
Program: #include <stdio.h> #include <stdlib.h>

struct Node { int data; struct Node *next; };

struct Node *front = NULL; struct Node *rear = NULL;

void enqueue(int value) { struct Node *newNode;

newNode = (struct Node *)malloc(sizeof(struct Node));

newNode->data = value;
newNode->next = NULL;

if (front == NULL)
{
    front = newNode;
    rear = newNode;
}
else
{
    rear->next = newNode;
    rear = newNode;
}
}

int peek() { if (front == NULL) { return -1; }

return front->data;
}

int main() { int value;

enqueue(10);
enqueue(20);
enqueue(30);
enqueue(40);

value = peek();

if (value == -1)
{
    printf("Queue is empty.");
}
else
{
    printf("Peek element of the queue = %d", value);
}

return 0;
}

Output:

<img width="832" height="296" alt="image" src="https://github.com/user-attachments/assets/dcfe74ff-1b7f-47f0-8cc3-8b46b6ad5977" />

Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.
