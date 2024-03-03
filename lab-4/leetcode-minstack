#include <stdlib.h>

typedef struct {
    int val;
    int min;
} Node;

typedef struct {
    Node* stack;
    int top;
    int capacity;
} MinStack;

MinStack* minStackCreate() {
    MinStack* stack = (MinStack*)malloc(sizeof(MinStack));
    stack->stack = (Node*)malloc(sizeof(Node) * 10000); // Assuming a maximum capacity of 10000
    stack->top = -1;
    stack->capacity = 10000;
    return stack;
}

void minStackPush(MinStack* obj, int val) {
    if (obj->top == -1) {
        obj->stack[++(obj->top)].val = val;
        obj->stack[obj->top].min = val;
    } else {
        obj->top++;
        obj->stack[obj->top].val = val;
        obj->stack[obj->top].min = (val < obj->stack[obj->top - 1].min) ? val : obj->stack[obj->top - 1].min;
    }
}

void minStackPop(MinStack* obj) {
    if (obj->top >= 0) {
        obj->top--;
    }
}

int minStackTop(MinStack* obj) {
    if (obj->top >= 0) {
        return obj->stack[obj->top].val;
    } else {
        // Handle empty stack case
        return -1; // You may choose a different way to signal an error or handle this case.
    }
}

int minStackGetMin(MinStack* obj) {
    if (obj->top >= 0) {
        return obj->stack[obj->top].min;
    } else {
        // Handle empty stack case
        return -1; // You may choose a different way to signal an error or handle this case.
    }
}

void minStackFree(MinStack* obj) {
    free(obj->stack);
    free(obj);
}
