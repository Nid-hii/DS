#include <stdio.h>
#include <stdlib.h>

#define MAX 6

int Q[MAX];
int front = -1, rear = -1;

void insert(int element) {
    if (rear == MAX - 1) {
        printf("Queue overflow\n");
        exit(1);
    }

    if (front == -1) {
        front = 0;
    }

    rear++;
    Q[rear] = element;

    printf("%d inserted into the queue\n", element);
}

void delete() {
    if (front == -1) {
        printf("Queue underflow\n");
        exit(1);
    }

    int deletedElement = Q[front];
    front++;

    printf("%d deleted from the queue\n", deletedElement);
}

void display() {
    if (front == -1) {
        printf("Queue underflow\n");
        exit(1);
    }

    printf("Queue elements: ");
    for (int i = front; i <= rear; i++) {
        printf("%d ", Q[i]);
    }
    printf("\n");
}

int main() {
    int choice, element;

    do {
        printf("\n1. Insert\n2. Delete\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter element to insert: ");
                scanf("%d", &element);
                insert(element);
                break;
            case 2:
                delete();
                break;
            case 3:
                display();
                break;
            case 4:
                printf("Exiting the program\n");
                break;
            default:
                printf("Invalid choice\n");
        }

    } while (choice != 4);

    return 0;
}

3B)
#include <stdio.h>
#include <stdlib.h>

#define SIZE 5

int CQ[SIZE];
int front = -1, rear = -1;

void cir_enqueue(int element) {
    if ((rear + 1) % SIZE == front) {
        printf("Circular Queue overflow\n");
        exit(1);
    }

    if (front == -1) {
        front = 0;
    }

    rear = (rear + 1) % SIZE;
    CQ[rear] = element;

    printf("%d inserted into the circular queue\n", element);
}

void cir_dequeue() {
    if (front == -1) {
        printf("Circular Queue underflow\n");
        exit(1);
    }

    int deletedElement = CQ[front];
    front = (front + 1) % SIZE;

    printf("%d deleted from the circular queue\n", deletedElement);
}

void display() {
    if (front == -1) {
        printf("Circular Queue underflow\n");
        exit(1);
    }

    int i = front;
    printf("Circular Queue elements: ");
    do {
        printf("%d ", CQ[i]);
        i = (i + 1) % SIZE;
    } while (i != (rear + 1) % SIZE);
    printf("\n");
}

int main() {
    int choice, element;

    do {
        printf("\n1. Insert\n2. Delete\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter element to insert: ");
                scanf("%d", &element);
                cir_enqueue(element);
                break;
            case 2:
                cir_dequeue();
                break;
            case 3:
                display();
                break;
            case 4:
                printf("Exiting the program\n");
                break;
            default:
                printf("Invalid choice\n");
        }

    } while (choice != 4);

    return 0;
}
