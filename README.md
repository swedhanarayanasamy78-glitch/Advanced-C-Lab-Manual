EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST. Aim: To write a C program to search a given element in the given linked list.

Algorithm:

Define the structure for a node in a linked list.
Define the search function to find a specific character in the linked list.
Initialize the head of the linked list as needed.
Call the search function and perform other linked list operations as needed.
Program:

#include <stdio.h> #include <stdlib.h>

struct Node { int data; struct Node *next; };

int main() { struct Node *head = NULL; struct Node *temp; struct Node *newNode; int n, i, search, position = 1, found = 0;

printf("Enter the number of nodes: ");
scanf("%d", &n);

for (i = 0; i < n; i++)
{
    newNode = (struct Node *)malloc(sizeof(struct Node));

    printf("Enter element %d: ", i + 1);
    scanf("%d", &newNode->data);

    newNode->next = NULL;

    if (head == NULL)
    {
        head = newNode;
    }
    else
    {
        temp = head;

        while (temp->next != NULL)
        {
            temp = temp->next;
        }

        temp->next = newNode;
    }
}

printf("Enter the element to search: ");
scanf("%d", &search);

temp = head;

while (temp != NULL)
{
    if (temp->data == search)
    {
        printf("Element %d found at position %d.\n",
               search, position);
        found = 1;
        break;
    }

    temp = temp->next;
    position++;
}

if (found == 0)
{
    printf("Element %d not found in the linked list.\n", search);
}

return 0;
}

Output:

<img width="853" height="426" alt="648415645-a507968c-cc45-40c9-87e8-d0e90f3a0f1c" src="https://github.com/user-attachments/assets/44a5b969-12d2-4055-900e-18fd64e5dbc3" />

Result: Thus, the program to search a given element in the given linked list is verified successfully.

EXP NO:17 PROGRAM TO INSERT A NODE IN A LINKED LIST. Aim: To write a C program to insert a node in a linked list. Algorithm:

Define the structure for a node in a linked list
Define the insert function to insert a new node with character data at the end of the linked list.
Initialize the head of the linked list as needed.
Call the insert function and perform other linked list operations as needed.
Program:

#include <stdio.h> #include <stdlib.h>

struct Node { int data; struct Node *next; };

void insert(struct Node **head, int value) { struct Node *newNode; struct Node *temp;

newNode = (struct Node *)malloc(sizeof(struct Node));

newNode->data = value;
newNode->next = NULL;

if (*head == NULL)
{
    *head = newNode;
}
else
{
    temp = *head;

    while (temp->next != NULL)
    {
        temp = temp->next;
    }

    temp->next = newNode;
}
}

void display(struct Node *head) { struct Node *temp = head;

while (temp != NULL)
{
    printf("%d ", temp->data);
    temp = temp->next;
}
}

int main() { struct Node *head = NULL; int n, i, value;

printf("Enter the number of nodes: ");
scanf("%d", &n);

for (i = 0; i < n; i++)
{
    printf("Enter element %d: ", i + 1);
    scanf("%d", &value);

    insert(&head, value);
}

printf("\nLinked list after insertion:\n");
display(head);

return 0;
}

Output:

<img width="847" height="393" alt="648415869-9e539e01-ffa7-45d8-8d8b-ccaa53c34da5" src="https://github.com/user-attachments/assets/ea5ac11c-fd7a-4605-a24d-ea2bd5d3b863" />

Result: Thus, the program to insert a node in a linked list is verified successfully.

EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST Aim: To write a C program to traverse a doubly linked list.

Algorithm:

Initialize a temporary pointer (temp) to the head of the list.
Use a while loop to traverse the list until the end (temp == NULL) is reached.
Inside the loop, print the data of the current node.
Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
Program:

#include <stdio.h> #include <stdlib.h>

struct Node { int data; struct Node *prev; struct Node *next; };

int main() { struct Node *head = NULL; struct Node *temp; struct Node *newNode; int n, i;

printf("Enter the number of nodes: ");
scanf("%d", &n);

for (i = 0; i < n; i++)
{
    newNode = (struct Node *)malloc(sizeof(struct Node));

    printf("Enter element %d: ", i + 1);
    scanf("%d", &newNode->data);

    newNode->prev = NULL;
    newNode->next = NULL;

    if (head == NULL)
    {
        head = newNode;
    }
    else
    {
        temp = head;

        while (temp->next != NULL)
        {
            temp = temp->next;
        }

        temp->next = newNode;
        newNode->prev = temp;
    }
}

printf("\nDoubly linked list elements:\n");

temp = head;

while (temp != NULL)
{
    printf("%d ", temp->data);
    temp = temp->next;
}

return 0;
}

Output:

<img width="840" height="382" alt="648416164-06c88a6e-e828-4f72-881a-9e5c9abb5287" src="https://github.com/user-attachments/assets/21219206-6033-481c-8ccd-efb33371ef3b" />

Result: Thus, the program to traverse a doubly linked list is verified successfully.

EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST Aim: To write a C program to insert an element in doubly linked list

Algorithm:

Create a new node (newNode) and allocate memory for it.
Set the data of the new node to the provided value.
If the list is empty, set the new node as the head.
If the list is not empty, traverse the list to find the last node.
Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
Program: #include <stdio.h> #include <stdlib.h>

struct Node { int data; struct Node *prev; struct Node *next; };

void insert(struct Node **head, int value) { struct Node *newNode; struct Node *temp;

newNode = (struct Node *)malloc(sizeof(struct Node));

newNode->data = value;
newNode->prev = NULL;
newNode->next = NULL;

if (*head == NULL)
{
    *head = newNode;
}
else
{
    temp = *head;

    while (temp->next != NULL)
    {
        temp = temp->next;
    }

    temp->next = newNode;
    newNode->prev = temp;
}
}

void display(struct Node *head) { struct Node *temp = head;

while (temp != NULL)
{
    printf("%d ", temp->data);
    temp = temp->next;
}
}

int main() { struct Node *head = NULL; int n, i, value;

printf("Enter the number of elements: ");
scanf("%d", &n);

for (i = 0; i < n; i++)
{
    printf("Enter element %d: ", i + 1);
    scanf("%d", &value);

    insert(&head, value);
}

printf("\nDoubly linked list after insertion:\n");
display(head);

return 0;
}

Output:

<img width="855" height="442" alt="648416385-050ae48c-95b2-4b1e-9a83-1ee49f000955" src="https://github.com/user-attachments/assets/de26b1d9-c922-4a4a-aef8-0565a09450d6" />

Result: Thus, the program to insert an element in doubly linked list is verified successfully.

EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

Aim: To write a C function that deletes a given element from a linked list.

Algorithm:

Check if the Linked List is Empty: o If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
Traverse the Linked List: o Start from the head node and iterate through the list to find the node that contains the given element (data).
Handle Deletion of the First Node: o If the element to be deleted is found in the head node:  Update the head of the linked list to point to the next node (i.e., head = head->next).  Free the memory allocated to the node to be deleted.  Exit the function.
Traverse and Delete from the Middle or End: o If the element is not in the head node, continue traversing the list by checking each node’s next pointer. o When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next). o Free the memory allocated to the node to be deleted.
Handle the Case when the Element is Not Found: o If the element is not found in any node, print a message indicating the element is not present in the list.
End the Function.
Program: #include <stdio.h> #include <stdlib.h>

struct Node { int data; struct Node *next; };

void deleteElement(struct Node **head, int value) { struct Node *temp; struct Node *prev;

if (*head == NULL)
{
    printf("Linked list is empty.\n");
    return;
}

temp = *head;
prev = NULL;

while (temp != NULL && temp->data != value)
{
    prev = temp;
    temp = temp->next;
}

if (temp == NULL)
{
    printf("Element %d not found.\n", value);
    return;
}

if (prev == NULL)
{
    *head = temp->next;
}
else
{
    prev->next = temp->next;
}

free(temp);

printf("Element %d deleted successfully.\n", value);
}

void display(struct Node *head) { struct Node *temp = head;

while (temp != NULL)
{
    printf("%d ", temp->data);
    temp = temp->next;
}
}

int main() { struct Node *head = NULL; struct Node *newNode; struct Node *temp;

int n, i, value;

printf("Enter the number of nodes: ");
scanf("%d", &n);

for (i = 0; i < n; i++)
{
    newNode = (struct Node *)malloc(sizeof(struct Node));

    printf("Enter element %d: ", i + 1);
    scanf("%d", &newNode->data);

    newNode->next = NULL;

    if (head == NULL)
    {
        head = newNode;
    }
    else
    {
        temp = head;

        while (temp->next != NULL)
        {
            temp = temp->next;
        }

        temp->next = newNode;
    }
}

printf("\nLinked list before deletion:\n");
display(head);

printf("\n\nEnter the element to delete: ");
scanf("%d", &value);

deleteElement(&head, value);

printf("\nLinked list after deletion:\n");
display(head);

return 0;
}

Output:

<img width="848" height="522" alt="image" src="https://github.com/user-attachments/assets/38f0eab3-75a7-42ed-accf-10fede297220" />

Result: Thus, the function that deletes a given element from a linked list is verified successfully.
