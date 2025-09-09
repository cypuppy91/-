# 알고리즘
 
가상 컴퓨터 + 가상 언어 + 가상 코드
RAM = cpu + memory + 기본 연산(단위 시간에 수행되는 연산)

기본연산(모두 1단위 시간이라 가정) : 
배정, 대입, 복사연산, 산술연산, 비교연산, 논리연산, 비트연산 

가상 언어의 조건 : 기본연산, 비교, 반복문, 함수
가상 코드 : 이런 가상의 언어로 코드를 작성

# 자료구조, 알고리즘의 시간 복잡도

1. 모든 입력에 대해 기본 연산 횟수를 더한 후 평균 : 현실적으로 불가능
2. 가장 안좋은 입력에 대한 기본 연산 횟수를 측정 => 어떤 입력에 대해서도 이거보다 수행 시간이 크지 않음

 일반적으로 알고리즘 수행시간 = 최악의 입력에 대한 기본 연산 횟수
수행시간 T(n)

 <img width="194" height="140" alt="image" src="https://github.com/user-attachments/assets/7c1a5dcf-db5e-42a6-8e3f-5624996e34c9" />  T(n) = 4n + 1
 
 <img width="272" height="181" alt="image" src="https://github.com/user-attachments/assets/e537b09d-8364-4f28-9538-5d3289467a5a" /> T(n) = 3/2n^2 + 3/2n + 1


# BIG - O 표기법
 
1. T1(n) = 2n-1                      
2. T2(n) = 4n+1                        
3. T3(n) = 3/2n^2 + 3/2n + 1

1. T1이 T2 보다 2배 느리다 = 참
2. T3는 n<5/3이면 T2보다 빠르다, 모든 n에 대해서 T1보다 느리다
3. T3는 n > 5/3 이면 항상 T2보다 느리다

결국 T1, T2, T3는 N에 대해 최고차항이 선형적으로 증가 or 제곱으로 증가
최고 차항만 수행시간을 표기해도 어느정도 나옴

수행시간 T(n) = 함수 값을 결정하는 최고 차항만으로 간단하게 표기
T1(n) = 2n-1 -> T1(n) = O(n)
T2(n) = 4n+1 -> T2(n) = O(n)
T3(n) = 3/2n^2 + 3/2n + 1 -> T3(n) = O(n^2)

1. 최고 차항만 남긴다
2. 최고 차항 계수(상수)는 생략한다
3. Big - O(최고차항)

<img width="163" height="144" alt="image" src="https://github.com/user-attachments/assets/c867b780-c8f4-411a-8384-92f55273719c" /> 
while문의 경우 
<img width="358" height="305" alt="image" src="https://github.com/user-attachments/assets/a0c405b6-750b-4810-95fb-9a26393c3c4b" />


# 배열과 리스트
가장 기본적인 순차적인 자료구조
C 언어의 배열은 읽기와 쓰기가 상수 시간(O(1)) 안에 가능하다. 주소를 할당 시키고 거기에 배열 값을 넣
파이썬의 리스트는 주소를 가르키는 역할 A[0] -> 0 을 가리킬때 A[0] = A[0] + 1 을 할 경우 A[0]은 새로 1을 가리킨다
A.append(6) : 맨 뒤에 6을 삽입

A.pop() : 맨뒤의 값을 지우고 리턴

A.insert(1,10) : A[1]에 10을 삽입

A.remove(value) : A에서 value 제거

A.index(value),A.count(value)

리스트 : 용량 자동 조절 가능 (dynamic array)
배열 : 자동 조절 X, 함수로 메모리를 새로 만들어준 다음 대입 해야 함

코드 실행하면 56, 88이 나옴

결국 리스트의 append도 자동으로 해주지만 c와 똑같이 작동해서 시간은 O(1)

# 순차적 자료구조

1. 배열, 리스트
    - index로 임의의 원소를 접근
    - 연산자 []
    - 삽입(append, insert)
    - 삭제(pop,remove)

2. stack, queue, dequeue
    - 제한된 접근(삽입, 삭제)만 허용
    - stack : LIFO(Last In First Out)
    - queue : FIFO(First In First Out)
    - dequeue : stack + queue

3. linked list(연결 리스트)
    - 각각의 값은 자기 자신의 값과 다음 값의 주소를 가지고 있다. 마지막은 None
    - 인덱스로 접근 X
    - 오래 걸리는게 단점
