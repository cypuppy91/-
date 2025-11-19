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

# STACK
삽입 : push 
삭제 : pop
top(맨위값 리턴), len(개수)

<img width="650" height="566" alt="image" src="https://github.com/user-attachments/assets/1413a10e-4a28-4b09-abac-4592ed7cadfd" />

예 1) 괄호 맞추기

스택 예 2) 계산기 코드 작성

2+3*5 -> infix 수식`
infix -> postfix 수식으로 바꾸기
2 3 5 * +
1. 괄호 치기 (2+(3*5))
2. 연산자의 오른쪽 괄호 다음으로 연산자 이동
3. 괄호 지우기

3 * (2 + 5) * 4
-> ((3 * (2+5)) * 4)
3 2 5 + * 4 *

infix -> postfix
리스트 : outstack
스택 : opstack
 
<img width="464" height="682" alt="image" src="https://github.com/user-attachments/assets/8be9de75-6313-4825-bbd2-8377c7e26a90" /><img width="346" height="443" alt="image" src="https://github.com/user-attachments/assets/56ad90b8-b9c7-40cb-a27b-c2b95979ac40" />

<img width="85" height="43" alt="image" src="https://github.com/user-attachments/assets/583c7ed0-38bf-417b-9fec-4b8a3540e272" /><img width="60" height="40" alt="image" src="https://github.com/user-attachments/assets/9a01927b-7c9d-4415-b7b0-36d2f86524ae" /><img width="53" height="46" alt="image" src="https://github.com/user-attachments/assets/b80b39ab-906b-4e12-a889-0d5106a97f6f" />


# 큐(queue)

큐 : FIFO (First-In-First_out) 규칙의 순차적 자료구조
삽입 : enqueue
삭제 : dequeue : 양쪽 끝으로 나가고 들어갈수있음


# 연결리스트(Linked List)

연결리스트 : key 값과 link값 존재(속도가 list보다 빠름)

한방향 vs 양방향
한방향 : 키와 링크
양방향 : 키와 링크 2

삽입 연산
pushFront(앞쪽에 생성 삽입) : O(1)
pushBack(뒤쪽에 생성 삽입) : O(n)

삭제 연산
popFront : O(1)
popBack : O(n)

한방향 연결리스트 추가 연산 : 탐색과 제너레이터

연결리스트는 for문을써서 돌리기가 불가능



그때 쓰는게 제너레이터 특히 yield v (return과 비슷) 중요

iterator를 사용하면 편하게 한방향 연결리스트에서 for문 사용 가능

양방향 연결리스트(Doubly Linked List)

양방향 연결리스트에서의 노드는 key값과 prev값, next값의 3개가 필요

양방향 연결리스트를 끝과 끝을 연결한 연결리스트는 원형 양방향 연결리스트

원형 양방향 연결리스트(양방향 연결리스트는 원형이라 가정)

원형 양방향 연결리스트에서 첫 값을 알기위해 더미 노드 생성

양방향 연결리스트
class Node :
 def __init__(self,key=None):
   self.key = key
   self.next = self
   self.prev = self

class Doubly LinkedList:
 def __init__(self):
  self.head = node()
  self.size = 0
 ...

# 연결 리스트의 연산
splic 연산
  def splic(self,a,b,x):
   조건 1 : a -> ... -> b
   조건 2 : a와 b 사이에 head X
   ap = a.prev, bn = b.next, xn = x.next
   ap.next = bn
   bn.prev = ap
   x.next = a
   a.prev = x
   b.next = xn
   xn.prev = b

삽입연산
insertAfter(x,key) => moveAfter(node(key) , x)
insertBefore(x,key) => moveBefore(node(key),x)

pushFront(key) => insertAfter(self.head,key)
pushBack(key) => insertBefore(self.head,key)

이동연산 
moveAfter(self,a,x) => splic(a,a,x)
moveBefore(a,x) => splic(a,a,x.prev)

삭제 연산
remove(x)
if x == None or x == self.head:
 return x
x.prev.next = x.next
x.next.prev = x.prev

popFront
popBack

탐색 연산
def search(self,key) :
 v = self.head
 while v.next != self.head:
  if v,key == key:
   return v
   v = v.next
 return None
 
n개의 노드를 가지는 이중 연결 리스트의 시간 복잡도

search(key) : O(n)
이동연산 :  O(1)
remove : O(n)

# 해시 테이블 : Hash Table

해시 테이블은 매우 빠른 평균 삽입, 삭제, 탐색 연산 제공
삽입 삭제 탐색이 모두 O(n) 속도임

# 해시 함수
나머지 연산을 활용한 해시 함수를 
Division head func
f(k) = k%m
f(k) = (k%p)%m

충돌이 하나도 안나타나고 1-1 슬롯인 해시함수를 퍼펙트 해시함수라함
unviersal h.f : x와 y의 키값이 같은 함수를 나타낼 확률이 1/m일때
여러 함수가 있음

좋은 해시 함수의 조건
1. 작은 충돌 (계산이 느려짐)
2. 계산이 빠름 (충돌이 많아짐)

# 충돌회피방법(collision resolution method)

- open addressing : 충돌이 날 경우 그 곳에는 값이 있지만 대신 그 근처에 값을 저장하는 방법
  linear probing : 충돌이 일어나면 바로 밑에있는 곳으로 가서 처음 있는 빈칸에 값을 저장함
  guadratic probing : 충돌이 일어나면 제곱 밑으로 감 1^2 -> 2^2 -> 3^3 
  double hashing : hash 함수를 2개를 사용 f(key) + g(key) -> f(key) + 2g(key) -> '''

  linear probing : set(key, value = None):
   1. key값이 H에 있으면 value를 update
   2. key값이 H에 없으면 (key,value) 값을 insert
  remove(key)
  search(key)

 linear probing의 성능 평가는 cluster size의 크기에 영향을 받음
 cluster size는 hash function, Collision Resolution(충돌 해결), load factor(밀도 지표)에 영향을 받
   - load factor : 값의 개수/전체 해쉬테이플 크기
해쉬 테이블의 절반 이상이 빈 슬롯으로 맞추면 평균적으로 상수시간에 가능 O(1) 그래서 엄청 빠름

- chaining
해쉬 테이블의 각 슬롯에 한방향 연결 리스트를 만들어 관리함

# 트리구조
순차적 자료구조 : 배열 인덱스 i = 0,1,''', 부모 자식의 관계
연결리스트 링크 - 트리(Tree) , 이진트리(binary tree)

<img width="1000" height="673" alt="image" src="https://github.com/user-attachments/assets/77c62d50-5258-4849-908e-7644a7d7787a" />


# 힙(heap) : 합 성질을 만족하는 이진트리

<img width="410" height="317" alt="image" src="https://github.com/user-attachments/assets/7fec2c6d-11d5-4b40-97bf-c677235f022a" />

H = [a,b,c,null,d,e,f]

이 방식의 장점은 왼쪽 자식노드 오른쪽 자신노드가 어디 있는지 알 수 있다.
heap 성질 : 모든 부모 노드의 key 값은 자식노드의 key 값보다 작지 않다.
1. 모양을 만족해야하고
2. 힙 성질을 만족해야한다

make_heap : heapify_down
heapify_down = O(log n)
make_heap : O(nlog n) = O(n)

insert 연산 : O(log n)

find_max : O(1)

delete_max : O(log n)

search 함수는 존재하지 않음


# 이진트리(Binary Tree)

 - 이진 트리 -> 배열, 리스트 (heap)
 - 노드와 링크 직접

이진트리 순회 : 이진트리 노드의 key 값을 빠짐없이 출력하는 방법
preorder,inorder, postorder

<img width="317" height="319" alt="image" src="https://github.com/user-attachments/assets/52a35349-af8e-4aa9-ab81-4754dcda1565" />

preorder : F B A D C E G I H
inorder : A B C D E F G I H
postorder : A C E D B I H G F


# 이진 탐색 트리(Binary Search Tree) : BST

각 노드의 왼쪽 subtree의 key 값은 노드의 key 값보다 작거나 같아야 하고 오른쪽의 subtree의 key 값은 노드의 key 값보다 크거나 같아야 한다

search : # key값 노드가 있다면 해당 노드 return 없다면 노드가 삽입될 부모 노드 리턴
search 의 경우 if문으로 이루어져있기 떄문에 상수시간 O(h)






