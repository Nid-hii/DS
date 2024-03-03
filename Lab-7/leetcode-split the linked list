/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
struct ListNode** splitListToParts(struct ListNode* head, int k, int* returnSize) {
     struct ListNode* current = head;
    int length = 0;
    while (current) {
        length++;
        current = current->next;
    }
    int part_size = length / k;
    int extra_nodes = length % k;

    struct ListNode** result = (struct ListNode**)malloc(k * sizeof(struct ListNode*));
    current = head;
    for (int i = 0; i < k; i++) {
        struct ListNode* part_head = current;
        int part_length = part_size + (i < extra_nodes ? 1 : 0);
        for (int j = 0; j < part_length - 1 && current; j++) {
            current = current->next;
        }
        if (current) {
            struct ListNode* next_node = current->next;
            current->next = NULL;
            result[i] = part_head;
            current = next_node;
        } else {
            result[i] = NULL;
        }
    }
    *returnSize = k;
    return result;
}
