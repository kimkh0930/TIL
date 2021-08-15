## 크루스칼 알고리즘

> 가장 적은 비용으로 모든 노드를 연결하기 위해 사용하는 알고리즘
최소 신장 트리를 만들기 위한 대표적인 알고리즘
여러 개의 도시가 있을 때 각 도시를 도로로 연결하고자 할 때 최소비용으로 연결하기위한 알고리즘이다.

순서는
정렬된 순서에 맞게 그래프에 포함시킨다.
포함시키기 전에 사이클 테이블을 확인한다.
사이클을 형성하는 경우 간선을 포함하지 않는다.

```
Ex)
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

int getParent(int set[], int x) {
	if (set[x] == x) return x;
	return set[x] = getParent(set, set[x]);
}

int unionParent(int set[], int a, int b) {
	a = getParent(set, a);
	b = getParent(set, b);

	if (a < b)set[b] = a;
	else set[a] = b;
}

int find(int set[], int a, int b) {
	a = getParent(set, a);
	b = getParent(set, b);
	if (a == b)return 1;
	else return 0;
}

class Edge {
public:
	int node[2];
	int distance;
	Edge(int a, int b, int distance) {
		this->node[0] = a;
		this->node[1] = b;
		this->distance = distance;
	}
	bool operator<(Edge& edge) {
		return this->distance < edge.distance;
	}

};

int main(void) {
	int n = 7;
	int m = 11;

	vector<Edge> v;
	v.push_back(Edge(1, 7, 12));
	v.push_back(Edge(1, 4, 28));
	v.push_back(Edge(1, 2, 67));
	v.push_back(Edge(1, 5, 17));
	v.push_back(Edge(2, 4, 24));
	v.push_back(Edge(2, 5, 62));
	v.push_back(Edge(3, 5, 20));
	v.push_back(Edge(3, 6, 37));
	v.push_back(Edge(4, 7, 13));

	sort(v.begin(), v.end());


	int set[n];
	for (int i = 0; i < n; i++) {
		set[i] = i;
	}
```
