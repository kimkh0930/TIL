## 큐(Queue)

> 뒤쪽으로 들어가서 앞쪽으로 나오는 자료 구조 (선입선출)
이러한 특성 때문에 스케줄링, 탐색 알고리즘 등 다방면에서 활용됨
`Push`와 `pop`으로 이루어짐

### 배열을 이용한 큐

```
Ex)
#include <stdio.h>
#define SIZE 10000
#define INF 99999999

int queue[SIZE];
int front = 0;
int rear = 0;

void push(int data) {
	if (rear >= SIZE) {
		printf("큐 오버플로우가 발생했습니다. \n");
		return;
	}
	queue[rear++] = data; //큐의 뒤쪽부터 데이터를 넣음
}

int pop() {
	if (front == rear) {
		printf("큐 언더플로우가 발생했습니다.\n");
		return -INF;
	}
	return queue[front++]; //큐의 앞에서부터 데이터를 뺌
}

void show() {
	printf("---큐의 앞---");
	for (int i = front; i < rear; i++)
	{
		printf("%d\n", queue[i]);
	}

}
```

### 연결 리스트를 이용한 큐

```
Ex)

#include <stdio.h>
#define SIZE 10000
#define INF 99999999

typedef struct {
	int data;
	struct Node* next;
}Node;

typedef struct {
	Node* front;
	Node* rear;
	int count;
}Queue;

void push(Queue* queue, int data) {
	Node* node = (Node*)malloc(sizeof(Node));
	node->data = data;
	node->next = NULL;
	if (queue->count == 0) {
		queue->front = node;
	}
	else {
		queue->rear->next = node;
	}
	queue->rear = node;
	queue->count++;
}

int pop(Queue* queue) {
	if (queue->count == 0) {
		printf("큐 언더플로우가 발생했습니다.\n");
		return -INF;
	}
	Node* node = queue->front;
	int data = node->data;
	queue->front = node->next;
	free(node);
	queue->count--;
	return data;
}

void show(Queue* queue) {
	Node* cur = queue->front;
	printf("---큐의 앞---\n");
	while (cur != NULL) {
		printf("%d\n", cur->data);
		cur = cur->next;
	}
	printf("---큐의 뒤---\n");
}

```
