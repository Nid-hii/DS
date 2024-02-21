#include <stdio.h>
#include <stdlib.h>

struct ListNode {
    int data;
    struct ListNode* next;
};

struct ListNode* push(struct ListNode* top, int data) {
    struct ListNode* newNode = (struct ListNode*)malloc(sizeof(struct ListNode));
    newNode->data = data;
    newNode->next = top;
    return newNode;
}

struct ListNode* pop(struct ListNode* top) {
    if (top == NULL) {
        printf("Stack is empty.\n");
        return NULL;
    }

    struct ListNode* temp = top;
    top = top->next;
    printf("Popped element: %d\n", temp->data);
    free(temp);
    return top;
}


void printStack(struct ListNode* top) {
    printf("Stack: ");
    while (top != NULL) {
        printf("%d -> ", top->data);
        top = top->next;
    }
    printf("NULL\n");
}

int main() {
    struct ListNode* stackTop = NULL;

    // Pushing elements onto the stack
    stackTop = push(stackTop, 3);
    stackTop = push(stackTop, 5);
    stackTop = push(stackTop, 7);

    printStack(stackTop);

    
    stackTop = pop(stackTop);
    stackTop = pop(stackTop);

    printStack(stackTop);


    while (stackTop != NULL) {
        struct ListNode* temp = stackTop;
        stackTop = stackTop->next;
        free(temp);
    }

    return 0;
}
