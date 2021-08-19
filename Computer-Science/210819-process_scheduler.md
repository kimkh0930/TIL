## 스케쥴링 알고리즘

### FIFO(first in first out)

> CPU를 처음부터 끝까지 사용한다.
가장 간단한 스케쥴러이며 배치 처리 시스템과 유사하다
선입 선출의 작업을 한다.


### 최단 작업 우선(SJF) 스케쥴러

> Shortest job first의 약어로 가장 프로세스 실행시간이 짧은 프로세스부터 실행 시키는 알고리즘이다.

### 우선 순위 기반 스케쥴러

> Priority-based 스케쥴러라고도 불리며 정적 우선순위로 프로세스마다 우선순위를 미리 지정할 수 있으나 일반적으로 스케쥴러가 상황에 따라 우선순위를 동적으로 변경하는 동적 우선순위를 사용한다.

### Round Robin 스케쥴러

> 시분할 시스템을 기반으로 한 스케쥴러 

## 프로세스

> 실행 중인 프로그램을 의미 작업, task, job 이랑 혼용되어 사용된다.

### 프로세스 상태

> 프로세스 생성 –> 실행 가능(ready) (3) <–>(2) 실행중(running) –> 종료&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp^  &nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp                   ㅣ(1)
&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbspㄴ &nbsp&nbsp&nbsp&nbsp(4) 대기 (block) &nbsp&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp <ㅡ

* Running state – 현재 CPU에서 실행 상태
* Ready state - CPU에서 실행 가능(대기) 상태
* Block state – 특정 이벤트 발생 대기 상태

(1)	Cpu가 실행되고 있는 상황에서 멈추고 이벤트 대기 상태로 전환
(2)	스케쥴러가 프로세스를 골라 실행 상태로 전환
(3)	스케쥴러가 프로세스를 골라 대기 상태로 전환
(4)	특정 이벤트가 들어오면 다음에 실행하기 위해 ready로 전환

