#include<stdio.h>
#include<stdlib.h>
struct node {
    int data;
    struct node *next;
};
struct node *head = NULL;
void display() {
    printf("Elements are: ");
    struct node *ptr = head;
    while (ptr != NULL) {
        printf("%d -> ", ptr->data);
        ptr = ptr->next;
    }
    printf("NULL\n");
}
void insert_begin() {
    struct node *temp = (struct node*)malloc(sizeof(struct node));
    printf("Enter the value to be inserted: ");
    scanf("%d", &temp->data);
    temp->next = head;
    head = temp;
}
void delete_begin() {
    if (head == NULL) {
        printf("List is empty. Deletion not possible.\n");
        return;
    }
    struct node *temp = head;
    head = head->next;
    printf("Element deleted from the beginning: %d\n", temp->data);
    free(temp);
}
void delete_end() {
    if (head == NULL) {
        printf("List is empty. Deletion not possible.\n");
        return;
    }
    struct node *temp, *prev;
    temp = head;
    while (temp->next != NULL) {
        prev = temp;
        temp = temp->next;
    }
    if (temp == head) {
        head = NULL;
    } else {
        prev->next = NULL;
    }
    printf("Element deleted from the end: %d\n", temp->data);
    free(temp);
}
void delete_at_position() {
    int position;
    printf("Enter the position to delete: ");
    scanf("%d", &position);

    if (head == NULL) {
        printf("List is empty. Deletion not possible.\n");
        return;
    }
    struct node *temp, *prev;
    temp = head;
    if (position == 0) {
        head = head->next;
        printf("Element at position %d deleted successfully.\n", position);
        free(temp);
        return;
    }
    for (int i = 0; temp != NULL && i < position; i++) {
        prev = temp;
        temp = temp->next;
    }
    if (temp == NULL) {
        printf("Position %d is out of bounds.\n", position);
        return;
    }
    prev->next = temp->next;
    printf("Element at position %d deleted successfully.\n", position);
    free(temp);
}
int main() {
    int choice;
    while (1) {
        printf("\n 1. to insert at the beginning\n 2. to delete beginning\n 3. to delete at end\n 4. to delete at any position\n 5. to display\n 6. to exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
            case 1:
                insert_begin();
                break;
            case 2:
                delete_begin();
                break;
            case 3:
                delete_end();
                break;
            case 4:
                delete_at_position();
                break;
            case 5:
                display();
                break;
            case 6:
                exit(0);
                break;
            default:
                printf("Enter the correct choice\n");
                break;
        }
    }
    return 0;
