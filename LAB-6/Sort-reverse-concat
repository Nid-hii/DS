#include <stdio.h>
#include <stdlib.h>


struct ListNode {
    int data;
    struct ListNode* next;
};


struct ListNode* insertEnd(struct ListNode* head, int data) {
    struct ListNode* newNode = (struct ListNode*)malloc(sizeof(struct ListNode));
    newNode->data = data;
    newNode->next = NULL;

    if (head == NULL) {
        return newNode;
    }

    struct ListNode* current = head;
    while (current->next != NULL) {
        current = current->next;
    }

    current->next = newNode;
    return head;
}
void printList(struct ListNode* head) {
    while (head != NULL) {
        printf("%d -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

// Function to reverse the linked list
struct ListNode* reverseList(struct ListNode* head) {
    struct ListNode *prev = NULL, *current = head, *nextNode;

    while (current != NULL) {
        nextNode = current->next;
        current->next = prev;
        prev = current;
        current = nextNode;
    }

    return prev; // New head of the reversed list
}


struct ListNode* sortList(struct ListNode* head) {
    if (head == NULL || head->next == NULL) {
        return head; // Already sorted or empty list
    }

    int swapped;
    struct ListNode *ptr1, *ptr2 = NULL;

    do {
        swapped = 0;
        ptr1 = head;

        while (ptr1->next != ptr2) {
            if (ptr1->data > ptr1->next->data) {
                // Swap the data values
                int temp = ptr1->data;
                ptr1->data = ptr1->next->data;
                ptr1->next->data = temp;
                swapped = 1;
            }
            ptr1 = ptr1->next;
        }
        ptr2 = ptr1;

    } while (swapped);

    return head;
}

struct ListNode* concatenateLists(struct ListNode* list1, struct ListNode* list2) {
    if (list1 == NULL) {
        return list2;
    }

    struct ListNode* current = list1;
    while (current->next != NULL) {
        current = current->next;
    }

    current->next = list2;
    return list1;
}

int main() {
    struct ListNode* list1 = NULL;
    struct ListNode* list2 = NULL;

    list1 = insertEnd(list1, 3);
    list1 = insertEnd(list1, 1);
    list1 = insertEnd(list1, 4);


    list2 = insertEnd(list2, 5);
    list2 = insertEnd(list2, 9);
    list2 = insertEnd(list2, 2);

    printf("Original Linked List 1: ");
    printList(list1);

    printf("Original Linked List 2: ");
    printList(list2);

    list1 = sortList(list1);
    printf("Sorted Linked List 1: ");
    printList(list1);

    
    list2 = reverseList(list2);
    printf("Reversed Linked List 2: ");
    printList(list2);

    struct ListNode* concatenatedList = concatenateLists(list1, list2);
    printf("Concatenated Linked List: ");
    printList(concatenatedList);

    while (concatenatedList != NULL) {
        struct ListNode* temp = concatenatedList;
        concatenatedList = concatenatedList->next;
        free(temp);
    }

    return 0;
}
