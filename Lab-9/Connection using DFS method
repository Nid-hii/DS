#include <stdio.h>
#include <stdlib.h>

#define MAX_NODES 100
#define MAX_EDGES 100

int graph[MAX_NODES][MAX_NODES];
int visited[MAX_NODES];

void DFS(int start, int n) {
    visited[start] = 1;
    for(int i = 0; i < n; i++) {
        if(graph[start][i] == 1 && !visited[i]) {
            DFS(i, n);
        }
    }
}

int isConnected(int n) {
    DFS(0, n);

    for(int i = 0; i < n; i++) {
        if(!visited[i]) {
            return 0;
        }
    }

    return 1;
}

int main() {
    int n, m;
    printf("Enter the number of nodes and edges: ");
    scanf("%d %d", &n, &m);

    printf("Enter the edges:\n");
    for(int i = 0; i < m; i++) {
        int a, b;
        scanf("%d %d", &a, &b);
        graph[a][b] = 1;
        graph[b][a] = 1;
    }

    if(isConnected(n)) {
        printf("The graph is connected.\n");
    } else {
        printf("The graph is not connected.\n");
    }

    return 0;
}
