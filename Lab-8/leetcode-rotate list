/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */

struct ListNode* rotateRight(struct ListNode* head, int k) {
    if (head == NULL || k == 0) {
        return head;
    }
    struct ListNode* current = head;
    int length = 1;
    while (current->next != NULL) {
        current = current->next;
        length++;
    }
    k = k % length;
    if (k == 0) {
        return head;
    }
    current = head;
    for (int i = 1; i < length - k; i++) {
        current = current->next;
    }
    struct ListNode* newHead = current->next;
    current->next = NULL;
    current = newHead;
    while (current->next != NULL) {
        current = current->next;
    }
    current->next = head;
    return newHead;
}
