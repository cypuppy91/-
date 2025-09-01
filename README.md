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


