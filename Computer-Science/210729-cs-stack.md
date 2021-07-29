## 스택

> Push와 pop으로 이루어져 한쪽으로 들어가서 한쪽으로 나오는 자료 구조

## 배열을 이용한 스택

```
Ex)
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h> 
#include <stdlib.h>
#define SIZE 10000
#define INF 99999999

int stack[SIZE]; //공간을 미리 할당해야 하기 때문에 비효율적
int top = -1;

void push(int data) {
	if (top == SIZE - 1) { //size보다 많이 들어갈 경우를 방지
		printf("스택 오버플로우가 발생했습니다.\n");
		return;
	}
	stack[++top]= data;
}

int pop() {
	if (top == -1) { //더 이상 꺼낼 값이 없을 경우를 방지
		printf("스택 언더플로우가 발생했습니다.\n");
		return -INF;
	}
	return stack[top--];
}

void show() {
	printf("---스택의 최상단---\n");
	for (int i = top; i >= 0; i--) {
		printf("%d\n", stack[i]);
	}
	printf("---스택의 최하단---\n");
}
```


## 연결 리스트를 이용한 스택

```
Ex)
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h> 
#include <stdlib.h>
#define INF 99999999

typedef struct {
	int data;
	struct Node* next;
}Node;

typedef struct {
	struct Node* top;
}Stack;

void push(Stack* stack, int data) {
	Node* node = (Node*)malloc(sizeof(Node));
	node->data = data;
	node->next = stack->top;
	stack->top = node;
}

void pop(Stack* stack) {
	if (stack->top == NULL) {
		printf("스택 언더플로우가 발생했습니다.\n");
		return -INF;
	}
	Node* node = stack->top;
	int data = node->data;
	stack->top = node->next;
	free(node);
	return data;
}

void show(Stack* stack) {
	Node* cur = stack->top;
	printf("---스택의 최상단===\n");
	while (cur != NULL) {
		printf("%d\n", cur->data);
		cur = cur->next;
	}
	printf("---스택의 최하단===\n");

}

int main(void) {
	Stack s;
	s.top = NULL;
	push(&s, 7);
	push(&s, 5);
	push(&s, 4);
	pop(&s);
	push(&s,6);

	system("pause");
	return 0;
}

```
* 중위 표기법 - 사람이 수식을 표기할 때 사용하는 표기방법.
* 후위 표기법 - 컴퓨터가 계산하기 편한 표기법 연산자가 뒤쪽에 위치

### 중위 표기법을 후위 표기법으로

> 1.	피연산자가 들어오면 바로 출력
2.	연산자가 들어오면 자기보다 우선순위가 높거나 같은 것들을 빼고 자신을 스택에 담는다.
3.	여는 괄호 ‘(‘는 무조건 스택
4.	닫는 괄호 ‘)’를 만나면 ‘(‘를 만날 때까지 스택에서 출력

