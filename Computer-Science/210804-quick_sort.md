> 피벗을 기준으로 큰 값과 작은 값을 서로 교체하는 정렬 기법
값을 서로 교체하는데 N번, 엇갈린 경우 교체 이후에 원소가 반으로 나누어지므로 전체 원소를 나누는 데 평균적으로 logN번이 소요되므로 평균적으로 O(NlogN)의 시간 복잡도를 가진다.


피벗 값이 가장 왼쪽에 있다고 가정

```
Ex)
void quickSort(int start, int end) {
	if (start >= end)return;
	int key = start, i = start + 1, j = end, tmep; //i는 왼쪽에서 시작하는 위치 j는 오른쪽에서 시작하는 위치
	while (i <= j) { //엇갈릴 때까지 반복
		while (i <= end && a[i] <= a[key])i++; //a[i]에 키 값보다 큰 값이 들어가도록
		while (j > start && a[j] >= a[key])j--;//a[j]에 키 값보다 작은 값이 들어가도록
		if (i > j)swap(&a[key], &a[j]); //엇갈린 상태라면 키값과 j값을 바꿈
		else swap(&a[i], &a[j]); //엇갈리지 않았다면 i값과 j값을 바꿈
	}
	quickSort(start, j - 1); //엇갈린 상태에서 벗어나 두 구간으로 나뉘게 되면 재귀적으로 두 군데에서 위의 과정을 다시 실행
	quickSort(j + 1, end);
}
```

만약 편향된 분할이 발생한다면 연산의 양이 O(N^2)이 되기 때문에 효율적이라 보기 힘들다. 따라서 실제 정렬에서 구현되지는 않으며 O(NlogN)을 보장하는 다른 정렬을 쓰게 된다.

