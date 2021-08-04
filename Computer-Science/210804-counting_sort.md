> 크기를 기준으로 데이터의 개수를 세는 정렬 알고리즘
O(N)의 시간 복잡도를 가진다.

```
Ex)
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#define MAX_VALUE 10001 //크기로 정렬하기때문에 너무 커졌을 때의 낭비를 방지

int n,m;
int a[MAX_VALUE];



int main() {
	scanf("%d", &n);
	for (int i = 0; i < n; i++) { scanf("%d", &m); a[m]++; }//값이 입력 될 때마다 해당 인덱스를 1씩 증가
	for (int i = 0; i < MAX_VALUE; i++) {
		while (a[i] != 0) { printf("%d", i); a[i]--; } //해당 인덱스가 0보다 크다면 그 크기만큼 출력
	}
	system("pause");
}

```
데이터의 한계가 명확할 때 사용하면 좋은 정렬 알고리즘이다.

