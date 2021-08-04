> 자릿수를 기준으로 차례대로 데이터를 정렬하는 알고리즘
가장 큰 자릿수를 D라고 했을 때 O(DN)의 시간 복잡도를 가진다.

1의자리를 기준으로 낮은 순서로 정렬 -> 10의자리 -> … 으로 정렬한다.

#### 한 사이클을 돌 때 
먼저 자릿수 배열에 0~9까지 해당하는 숫자의 인덱스를 +1해준 후 
누적 값을 구해 정렬하여 누적 값에 해당하는 인덱스에 값을 넣어 
결과 배열에 정리한다.

```
Ex)
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#define MAX 10000 //최대 원소 개수를 설정

void radixSort(int* a, int n) {
	int res[MAX], maxValue = 0; //res는 결과 배열
	int exp = 1;
	for (int i = 0; i < n; i++) {
		if (a[i] > maxValue) maxValue = a[i]; //가장 큰 값을 구해서 자릿수를 구함
	}
	while (maxValue / exp > 0) { //가장 큰값의 자릿수 만큼 실행
		int bucket[10] = { 0 }; //bucket은 자릿수 배열
		for (int i = 0; i < n; i++)bucket[a[i] / exp % 10]++; //0~9까지의 자릿수 배열에 넣음
		for (int i = 1; i < 10; i++)bucket[i] += bucket[i - 1]; //자릿수 배열의 누적값을 구함 ex) 0자리에 1개 1자리에 1개가 들어가 있다면 0은 1, 1은 2가 된다.
		for (int i = n - 1; i >= 0; i--) {
			res[--bucket[a[i] / exp % 10]] = a[i]; //누적값에 해당하는 인덱스에 값을 넣어줌
		}
		for (int i = 0; i < n; i++)a[i] = res[i];
		exp *= 10; //1부터 10씩 곱해나가면서 자릿수를 올림
	}
}
```

계수 정렬 보다는 약간 느리나, 숫자가 매우 커도 사용 가능하다.

