# 🗂️ 스택과 큐

# 📂 스택
## 🔍 스택 개념

- 용어의 의미 : '쌓다' 라는 뜻을 가진 용어
- 후입선출(LIFO) 입출력 형태를 갖는 자료구조.

- 후입 선출 - (LIFO : Last In First Out)
  - 가장 늦게 들어간 요소가 가장 먼저 나오고 가장 먼저 들어간 요소가 가장 늦게 나옴
  - 즉, 가장 나중에 들어온 데이터를 먼저 처리할 때 사용
  - 동일한 구조와 크기의 자료를 한 방향으로 쌓음
  - '데이터를 쌓는다'는 개념으로 쉽게 뷔페에 쌓인 접시를 생각하면 됨
  - 제일 먼저 놓인(맨 아래) 접시가 아닌 제일 늦게 놓인(맨 위) 접시가 먼저 꺼내진다.

## 💻 스택 구조

- Bottom : 가장 밑에 있는 데이터 또는 그 데이터의 인덱스
- Top : 가장 위에 있는 데이터 또는 그 데이터의 인덱스
- Capacity : 데이터를 담기 위한 용적
- size : 데이터의 개수
- top을 통해서만 접근 가능 (삭제를 할 때도 top통함)
- top에 가장 위에 있는 자료는 가장 최근 자료

## 📌 스택 특징

- 데이터를 하나씩만 넣고 뺄 수 있음.
- 중간에 위치한 데이터 접근 불가


- 재귀 함수의 동작 흐름과 같은 구조
  - 재귀 함수: 함수 안에 자신의 함수를 다시 호출하는 함수


- top는 -1부터 시작하여 push를 하면 +1, pop을 하면 -1을 하는 방식으로 동작   
- 이를 통해 스택 오버플로우(stack overflow)와 스택 언더플로우(underflow)를 판단할 수 있음

- 스택 오버플로우(stack overflow)
  - 스택이 꽉 차서 더 이상 자료를 push 할 수 없는 경우인데도 push를 하는 경우
- 스택 언더플로우(stack underflow)
  - 스택이 텅 비어있는 경우에 다시 pop을 하여 스택의 값을 빼낼 것을 요구하는 경우
  - pop 연산 수행 시 더이상 삭제할 Data가 없을 때 발생하는 오류


- 스택 시간복잡도 Big O
  - Insertion O(1)
  - Deletion O(1)
  - Search O(n)

  - 삭제나 삽입시 맨 위에 데이터를 삽입하거나 삭제하기 때문에 시간복잡도는 늘 O(1)의 시간복잡도를 가짐
  - 하지만 특정 데이터를 찾을 때는 특정 데이터를 찾을 때까지 수행을 해야하므로 O(n)의 시간 복잡도를 가짐

## ✏️ 시간 복잡도

![img](https://github.com/hyowon6/likelion_Exercise/assets/128475094/593f1658-b794-49f9-9ba5-1b65cfae96f0)
### 🔍 개념
- 특정 알고리즘이 어떤 문제를 해결하는데 걸리는 시간
- 입력값의 변화에 따라 연산을 실행할 때, 연산 횟수에 비해 걸리는 시간
- 같은 결과를 갖는 프로그래밍 소스도 작성 방법에 따라 걸리는 시간이 달라지며,   
  같은 결과를 같는 소스라면 시간이 적게 걸리는 것이 좋은 소스

 ### 📚 시간 복잡도 표기 종류
- 최악 , 최고, 평균의 값을 표기
- Big-O - 최악의 경우를 나타냄
     - O(n): 최악의 경우 n번까지 수행되면 프로그램을 끝낼 수 있음
 - Big-Omega - 최적의 경우를 나타냄
      - O(n): 최소 n번은 수행되어야 프로그램을 끝낼 수 있음
- Theta - 평균 (Big-O 와 Big-Omega값의 평균값)

- 주로  Big-O 표기법 사용 (최악의 경우를 고려한다)
  - 평균인 세타 표기를 하면 가장 정확하고 좋겠지만 평가하기가 까다로움
  - 그래서 알고리즘이 최악일때의 경우를 판단하면 평균과 가까운 성능으로 예측하기 쉽기 때문 최악의 경우인 빅오를 사용

### 📈 시간복잡도 성능지표
여기서 x축(n)이란 입력되는 데이터의 수를 의미 , y축(N)은 수행시간을 의미

```faster O(1) < O(log n) < O(nlog n) < O(n²) < O(2ⁿ) slower```

slower로 갈수록(즉, 오른쪽 방향으로 갈수록) 효율성이 떨어짐

- O(1) (Constant)
  - 입력 데이터의 크기에 상관없이 언제나 일정한 시간이 걸리는 알고리즘
  - 데이터가 얼마나 증가하든 성능에는 변함없이 일정함을 나타내고 있음
  ```java
  int sum = (x+1)*x/2;
  // (x+1)이 한 번, *x가 한 번, /2가 한 번 계산
  // 합 : 4번 수행
  // Big-O 표기법으로는 1
  ```
- O(n) (Linear)
  - 입력 데이터의 크기에 비례해서 처리 시간이 걸리는 알고리즘
  - n이 1번 늘어날 때마다 처리시간이 1 증가하여 선형적으로 증가함 (n 크기만큼 처리시간이 증가)
  - 하나의 루프를 사용하여 단일 요소 집합을 반복 하는 경우 사용
  ```java
   int sum = 0; // 1번
   for(int i = 0; i<n; i++){ // int i =0이 한번, i++이 n번
	 sum+=i; // n번
   }
   // 합 : 2n+2의 연산이 수행
  // 최대 차항만 계수 없이 표기 하기 때문에 O(n)
    ```

- O(log₂ n) 
  - 입력 데이터의 크기가 커질수록 처리 시간이 로그(log: 지수 함수의 역함수)만큼 짧아지는 알고리즘
  - 예를 들어 데이터가 10배가 되면, 처리 시간은 2배가 됨
  ```java
  void Logarithmic(n){
	i = 1; //1
    while(i<n){ //log2 n+1
    	printf(i); //log2 n
        i = i * 2; //log2 n
     }
     }
     // ( i = i * 2)에 의해 2의 거듭제곱으로 커지기 때문
     // 탐색 범위를 절반씩 좁혀가기 때문에 데이터의 개수가 절반씩 줄어듬으로 log₂ 
  ```
- O(n log₂ n)
   - 데이터가 많아질수록 처리시간이 로그(log) 배만큼 더 늘어나는 알고리즘
   - 예를 들어 데이터가 10배가 되면, 처리 시간은 약 20배가 됨
  ```java
  void nlogn(n){
	for(int i=1;i<n;i++){ //n번 반복
    	j=1; //n
        while(j<n){ //log n+1
        	print(i,j); //log n
            j = j * 2;  //log n
        }
     }
   }
   // 합 :  3n + 3n log n
   // 최대차항의 계수 없이 표기 O(n log n)
   // 분할되는 깊이는 logN으로 비례. 합병해야하는 배열의 수는 많아지지만 총원소 수는 같음.
  ```
- O(n²)
  - 데이터가 많아질수록 처리시간이 급수적으로 늘어나는 알고리즘
  - 예를 들어 데이터가 10배가 되면, 처리 시간은 최대 100배가 됨
  - ex) 이중 for 문
    ```java
    int sum = 0;
    for(int i = 0; i<n; i++){
	  for(int j = 0; j<i;j++){
    	sum+=j;
    }
    }
    // 바깥쪽 반복문은 n번 0~(n-1)반복, 안쪽 반복문은 i번 i만큼 반복
    // 등차수열의 합공식(n*(n-1)/2)에 의해 
    // 최대 차항의 계수 없이 표기하게되면 O(n²)

    ```
- O(2ⁿ)
  - 데이터량이 많아질수록 처리시간이 기하급수적으로 늘어나는 알고리즘
  - ex) 피보나치 수열
   ```java
   public int fibonacci(int num){
        if (num <=1){
            return num;
        }
        else if (num ==2){
            return 1;
        }
        else {
            return fibonacci(num-1) + fibonacci(num-2);
        }
    }
    // 자기 자신을 다시 호출하는 재귀함수 형태
    // 다음 항을 알기 위해 전의 2개의 항을 호출
    // 트리모양으로 나타내면, 2번씩 트리의 높이만큼 반복하는 형태
   ```

## 🗃️ 스택 사용

- 웹 브라우저 방문기록 (뒤로 가기) : 가장 나중에 열린 페이지부터 다시 보여줌
- 실행 취소 (undo) : 가장 나중에 실행된 것부터 실행을 취소


- 깊이 우선 탐색에 사용
- 자료구조 중 DFS(Depth First Search)는 Stack을 이용해 구현 가능
- DFS란 그래프 탐색 중 한가지로 한 분기를 모두 탐색 후 다음 분기를 탐색하는 방식
    - 그래프란 노드와 노드를 연결을 하는 간선을 하나로 모아둔 비선형 자료구조
    - 노드(정점) : 데이터가 저장 되는 곳
    - 간선(링크) : 노드와 노드 사이의 관계를 나타내는 선


- 메소드 호출, 후위 표기법 재귀 알고리즘에서도 Stack을 사용
    - 수식 표기법
        1) 전위 표기법 : 연산자 먼저 표기 ex) +AB
        2) 중위 표기법 : 피연산자 사이 연산자 표기 ex) A+B
        3) 후위 표기법 : 연산자 나중에 표기 ex) AB+


## 💻 Java Stack 구현

- Java에서 Stack은 Vector 클레스에서 파생된 클래스 즉, Vector 제공 메서드를 사용할 수 있음
- java.util.stack 라이브러리 사용
- 스택의 선언
  - 형식 : Stack<타입> 스택 이름 = new Stack<>(); 형태로 선언
  - <타입>은 <> 안에 클래스 또는 Integer, String 등으로 지정이 가능하다.

## ✔️ 스택 메서드
- add(), push() : 하나씩 값을 추가하는 메서드   
- pop(): 추가된 값을 반환하여 삭제하는 메서드   
- clear() : 스택안에 있는 모든 내용을 삭제하는 메서드
>pop과 clear 메서드의 차이점
>- pop() : 스택을 제거하면서 제거 되는 값을 반환
>- clear() : 반환 값 없이 스택 안에 있는 모든 값을 삭제
```
        Stack<Integer> Intstack = new Stack<>();

        Intstack.push(1); //push와 add로 값을 추가하여 출력
        Intstack.push(2);
        Intstack.add(3);
        Intstack.add(4);
        System.out.println(Intstack);

        System.out.println(Intstack.pop());
        System.out.println(Intstack);//삭제 한뒤 남은 값은 1-2-3

        Intstack.clear();// 스택의 모든 자료를 삭제함
        System.out.println(Intstack);
        
```
> [1,2,3,4]  
> 4  
> [1,2,3]  
> []  


- peek(): 스택의 마지막 요소를 반환하는 메서드
  - 요소를 반환만 하기 때문에 스택에는 변화가 없음
  - 가장 먼저 사용되는 값을 반환함
  - 스택을 clear로 초기화 한 뒤, peek 메서드를 사용하면 스택에 값이 없기 때문에 
  EmptyStackException 예외가 발생 
- size(): 스택의 크기 출력하는 메서드
- isEmpty(), empty():스택의 공백 여부를 확인하는 메서드

```
        Stack<Integer> stack = new Stack<>(); //int형 스택 선언
        stack.push(1);     // stack에 값 추가
        stack.push(2);     
        stack.push(3);     
        System.out.println(stack); // [1, 2, 3]

        System.out.println(stack.peek()); // 3 -> 가장 상단에 있는 값을 출력
        System.out.println(stack.size());// 3 -> stack의 크기 출력
        System.out.println(stack.empty());// false -> stack이 비어있는제 check (비어있다면 true)

```
> 결과  
> [1, 2, 3]  
> 3  
> 3  
> false  
> true

- search() 메서드  
  - 스택 안에 인자를 검색하여 위치를 반환   
 단, 검색 되는 값은 인덱스 값이 아닌 스택에서 삭제되는 순서를 반환함
```java
        Stack<Integer> Intstack = new Stack<>();

        Intstack.push(1);
        Intstack.push(2);
        Intstack.push(3);
        Intstack.push(1);
        // 1-2-3-1 값이 스택에 들어가 있음

        System.out.println(Intstack.search(3));
        System.out.println(Intstack.search(1));

        Intstack.pop();
        System.out.println(Intstack.search(1));
        System.out.println(Intstack.search(4));

        Intstack.clear();
        System.out.println("clear 후의 검색 :  "+Intstack.search(3));

```
> 결과   
> 2  
> 1  
> 3  
> -1  
> 스택에 값을 1-2-3-1 순서로 삽입   
>  
> 3을 search 했을 때 3은 pop() 할 때, 두번째로 삭제되므로 2 출력   
> 같은 인자가 있을 경우는 마지막 인자의 위치를 반환하기 때문에 1은 첫번째로 삭제되므로 1출력   
> pop() 메서드를 한번 수행한 뒤에 1을 삭제시키고 다시 1을 검색헀을 경우 다음 1은   
> 스택의 맨 아래에 깔려 있기 때문에 마지막 위치인 3이 출력   
> 없는 값을 검색하면 -1이 출력됨 (공백포함)
> 
### 메서드 요약
```java
Stack<타입> stack = new Stack<>();
stack.push();  // push: 하나씩 값을 추가하는 메서드
stack.pop();  // pop: 추가된 값을 반환하여 삭제하는 메서드
stack.peek();  // top 꺼내오기, 스택의 가장 위에 있는 항목을 반환
stack.size();  // stack 크기 출력하는 메서드
stack.isEmpty();  // 스택의 공백 여부를 확인하는 메서드  * 빈 공간 = true
stack.contains(num);  // num 값 있는지 확인  * Vector 제공 메서드
stack.search(num); // 스택 안에 인자를 검색하여 위치를 반환
stack.clear();  // 모든 데이터 삭제 및 초기화하는 메서드
stack.toString();  // 모든 데이터를 출력하는 메서드
```

> 참고자료
 - https://velog.io/@db_jam/Java-스택Stack-자료구조-정리
- https://velog.io/@iacid123/자료구조-Stack스택
- https://gmlwjd9405.github.io/2018/08/14/algorithm-dfs.html
- https://lotuslee.tistory.com/48
- https://velog.io/@nana-moon/알고리즘-DFS깊이-우선-탐색-재귀-스택Stack
- https://velog.io/@hyowonng/%EC%8A%A4%ED%83%9D-%EC%A0%95%EB%A6%AC
- https://coding-factory.tistory.com/601
- https://gmlwjd9405.github.io/2018/08/03/data-structure-stack.html
- https://ittrue.tistory.com/200
- https://go-coding.tistory.com/5
- https://devuna.tistory.com/22
* * *
****
# 📂 큐

## 🔍 큐 개념

- 사전적 의미: 줄을 서다
- FIFO (First In First Out) 구조로 저장하는 선형 자료구조

- 선입 선출 - (LIFO : First In First Out)
  - 가장 먼저 삽입된 데이터가 가장 먼저 삭제
  - 즉, 가장 먼저 들어온 데이터를 먼저 처리할 때 사용
  - 놀이공원 입장 줄을 생각하면 됨
  - 제일 먼저 줄을 서는 사람이 제일 먼저 나감
  
## 💻 큐 구조

- Front : 맨 앞, 삭제연산만 수행되는 곳
- Rear : 맨 뒤, 삽입연산만 수행되는 곳 
- EnQueue: Rear에서 이루어지는 삽입연산
- DeQueue: Front에서 이루어지는 삭제연산
- 들어올 때 Rear로 들어오지만 나올때는 Front부터 빠짐
- 접근은 가장 첫 원소와 끝 원소로만 가능

## 📌 큐 특징

- 데이터를 하나씩만 넣고 뺄 수 있음
- 중간에 위치한 데이터 접근 불가


- 큐 오버플로우(Queue overflow)
  - 큐에 저장할 수 있는 데이터의 크기를 초과한 상태에서 put을 하는 경우
- 큐 언더플로우(Queue underflow)
  - 큐에 데이터가 전혀 없는 상태에서 get을 하는 경우
  - Queue가 비어있어 Data를 읽어올 수 없을 때 발생하는 오류


- 시간복잡도
Insertion O(1)
Deletion O(1)
Search O(n)
  - 큐의 enqueue와 dequeue 연산은 일반적으로 상수 시간(O(1))에 수행됨
  - 큐의 크기에 관계없이 항목을 삽입하거나 삭제하는 데에 동일한 시간이 소요

## 🗃️ 큐 사용

- 운영체제(스풀링, 프로세스 스케쥴링, 컴퓨터 버퍼 등)에서 Queue를 이용함
- CPU의 효율을 위해 Queue 사용  
  (CPU에서 데이터를 빠르게 큐에 저장하고 다른 작업 수행, 주변기기의 속도에 맞처 큐에서 자료를 출력하여 작업 수행)


- 너비 우선 탐색에 사용
- Stack을 사용하는 DFS의 반대 개념인 BFS(Breadth First Search) 너비 우선 탐색은 Queue을 이용해 구현 가능 
- BFS란 루트 노드에서 시작해서 인접한 노드를 먼저 탐색하는 방법

###  Java Queue 구현

- java에서 Queue는 클래스로 구현된 stack과 다르게 queue 메모리 구조를 별도의 인터페이스로 제공   
→ LinkedList 클래스를 이용해 인스턴스화 시킴
- 큐의 선언
- 형식 : Queue <타입> 큐 이름 = new LinkedList<>(); 형태로 선언
- <타입>은 <> 안에 클래스 또는 Integer, String 등으로 지정이 가능

## ✔️ 큐 메서드

- add() 또는 offer(): 큐의 끝(rear)에 데이터를 추가하는 메서드
  - 만약 삽입에 성공하면 true를 반환하고, 큐에 여유 공간이 없어 삽입에 실패하면 IllegalStateException을 발생시킴

- poll() 또는 remove(): 큐의 시작(front)에서 데이터를 제거하는 메서드  
- clear(): 큐의 모든 요소를 제거하는 메서드
> poll과 remove의 차이점  
> - poll은 큐가 비어 있으면 null 반환  
> - remove는 대기열이 비어있다면 예외를 발생시킴

```java
Queue<Integer> queue = new LinkedList<>(); //int형 queue 선언
		queue.add(1);     // queue에 값 추가
		queue.add(2);     
		queue.offer(3);   
		
		System.out.println(queue.poll());       // 1 -> queue에 첫번째 값을 반환하고 제거 비어있다면 null
		System.out.println(queue.remove());     // 2 -> queue에 첫번째 값 제거
		queue.clear();  // queue 초기화
		System.out.println(queue);      // []
```
> 결과   
> 1  
> 2  
> []


- peek(), element() : 프론트의 값을 참조하는 메서드
  - element 메서드는 비어 있다면 Exception을 출력함
- size(): 큐의 크기 출력하는 메서드  
- isEmpty(), empty(): 큐가 비어있는지 확인하는 메서드  
  - queue이 비어있는지 check (비어있다면 true)

```java
queue.add(1);     // queue에 값 추가
queue.add(2);     
queue.offer(3);   // [1,2,3]
		
System.out.println(queue.peek()); // 1 -> queue의 첫번째 값 참조 
System.out.println(queue.element()); // 3 -> queue의 크기 출력
System.out.println(queue.size()); // false -> queue이 비어있는지 check (비어있다면 true)
System.out.println(queue.isEmpty()); // 1 -> queue에 1이 있는지 check (있다면 true)
```
> 결과  
> 1  
> 1  
> 3  
> false

## 메서드 요약
```java
Queue<타입> queue = new LinkedList<>();
queue.add(data);  // data 삽입 후 성공시 return true  * 저장 공간 부족 IllegalStateException 발생
queue.offer(data);  // data 삽입 후 성공시 return true  * 실패시 return false
queue.poll();  // Front 제거 및 리턴  * 비어있으면 return null
queue.remove();  // Front 제거 및 리턴  * 비어있으면 NoSuchElementException 발생
queue.peek();  // Front 리턴(제거는 안함)  * 비어있으면 return null
queue.element();  // Front 리턴(제거는 안함)  * 비어있으면 NoSuchElementException 발생
queue.clear(); // 모든 데이터 삭제 및 초기화
queue.size()); // 큐 크기 출력
queue.isEmpty(); // 큐의 공백 여부 확인 * 빈 공간 = true
queue.empty(); // 큐의 공백 여부 확인 * 빈 공간 = true
```

## ❗ 큐 구현 단점 극복

- Front와 Rear의 Default 값은 -1부터 시작하며, Front == Rear는 Queue가 Empty 상태임을 의미
- Enqueue는 Rear에서 일어나니, Rear == Queue.size()-1 -> True라면 Queue는 Full 상태
  - Front에서 Dequeue가 일어났을 수도 있기 때문에 항상 Full 상태라고 말할 순 없음
  - 위 문제는 순차, 원형, LinkedList로 해결 가능

### 선형 큐 
- 배열(순차 자료구조)을 이용한 Queue
  - 순차 자료구조 : 논리적인 순서대로 메모리에 저장하는 구현 방식
- 크기가 제한적이고, 빈 공간을 사용하려면 모든 자료를 꺼내야되거나 옮겨야함
- front, rear는 증가만 하는 방식, 실제로는 front 앞쪽에 공간이 있더라도 삽입할 수 없는 경우가 발생할 수 있음
 - 실제 데이터는 삭제 때마다 한 칸 앞으로 이동시키지 않았고, 인덱스 단위로 큐의 연산을 진행했기 때문에 이를 꽉 찼다고 인식하기 때문

  

### 원형 큐 
- 선형 큐의 단점을 보완한 방식의 새로운 큐
- 실제로는 1차원 배열구조지만, 배열 끝에 이르면 다시 맨 앞으로 이어지는 점에서 원형 Queue라고 부름
- 선형 Queue와 다르게 Full 상태와 Empty 상태를 구분함
  - 그렇기 때문에 원형 Queue는 항상 하나의 공간을 비워둠
  - Front == Rear라면 원형 Queue는 공백 상태
- 다시 맨 앞으로 돌아가는 방법은 ```rear = (rear + 1) % Queue 배열크기``` 를 해주면 됨
  - Full 상태인지 확인하는 방법도 동일하게 ```front = (rear +1) % Queue 배열크기```를 하면 됨  
  - Data가 추가되어 Front가 Queue 끝에 닿으면서 원형으로 구현됨



### LinkedList 큐 
- 큐의 단점을 극복하기 위해 가장 많이 사용하는 방식
- 연결리스트를 사용하기 때문에 큐의 길이를 가변적으로 할 수 있어 오버플로우가 발생하지 않는 것이 특징
- 필요에 따라 환형으로 만들 수도 있으며, 환형으로 만들지 않아도 삽입과 삭제가 제한되지 않아 편리함

> 출처  
https://bambbang00.tistory.com/5  
https://go-coding.tistory.com/6  
https://velog.io/@gillog/큐Queue  
https://you88.tistory.com/30  
https://leejinseop.tistory.com/36  
https://leejinseop.tistory.com/37  
https://yoongrammer.tistory.com/m/46  
https://coding-factory.tistory.com/602  
https://crazykim2.tistory.com/571  
https://93jpark.tistory.com/103  


-----
# 📂 데큐 deque 

## 🔍 데큐 정의
- Double ended :양 끝이 닮은, 양 끝이 앞이 되는 , 앞 뒤가 없는 의 뜻
  즉, depue는 양 끝이 앞 뒤가 되는 큐
- 스택과 큐의 장점을 모아서 만들어진 자료구조 ( FIFO 이지만 양쪽에서 들어오고 나갈 수 있음.)
- ex) 터널과 비슷한 구조를 가질 수 있음. 터널은 양쪽으로 들어갈수도 나갈 수도 있기 때문
  cf. depue 의 파생으로 스크롤과 셸프가 존재 
  - 스크롤 : 입력이 한쪽 끝으로만 가능 (입력 제한)
  - 셸프 : 출력이 한쪽 끝으로만 가능(출력제한)

## 📌 데큐 특징
- 데이터를 양쪽에서 삽입한 곳에서는 삭제가 가능한 구조
- 데이터 입력 순서와 상관없이 출력 순서 조절 가능
- 삽입 삭제 연산은 마찬가지로 O(1) 의 시간 복잡도를 가지고, 스택/큐와 달리 index 를 통해 요소들에 탐색이 가능하므로   
  이 역시 O(1)의 시간 복잡도를 가짐
- 따라서, push와 pop이 빈번한 알고리즘의 경우, list보다 deque를 사용하는것이 효율적이며 속도가 더 빠름

## 💻 데큐 구조
- 앞부분은 front 마지막은 last로 표현
- push는 push_front(),push_back()
- pop은 pop_front(), pop_back()

## 데큐 동작
- 데큐의 중간 지점을 mid라고 함
- 첫 시작은 front와 last 모두 mid에서 시작함
- front나 last의 위치가 같으면 mid로 초기화 
- 큐가 가득 찬 상태로 데이터가 들어오면 정렬을 실행함  
-> 모든 원소를 가득차지 않은곳으로 한칸씩 밀어 앞부분에 공간을 만들어줌  
-> 생긴 공간에 데이터를 추가

## 🗃️ 데큐 사용법
| 사용           | 내용                                                                                                    |
|--------------|-------------------------------------------------------------------------------------------------------|
| push_front() | 첫 입력 X<br/>1.--Front;<br/>2.Array[front] = data;  <br/>첫 입력 <br/>1.Array[Front] = data;<br/>2.++Last; |
| push_Last()  | 첫 입력 X<br/>1.--Last;<br/>2.Array[Last] = data;<br/> 첫 입력 <br/>1.Array[Last] = data;<br/>2.--front;    |
| pop_front()  | 1.Array[front] =null<br/>2.++front;                                                                   |
| pop_Last()   | 1.Array[Last] =null<br/>2.--Last;                                                                     |


## ✔️ 데큐 메소드
getBuffer(): 데이터 전체 획득    
isEmpty(): 비어있는지 확인  
pushFront(), pushBack(): 데이터 추가  
popFront(), popBack(): 데이터 삭제  
front(): 첫번째 데이터 반환   
back(): 끝 데이터 반환  
size(): 크기 확인  
clear(): 전체삭제  

### ❗ collections.deque의 메소드들 중 list와 차이를 보이는 메소드들
appendleft(x) : x를 데크의 왼쪽 끝에 삽입  
pop() : 데크의 오른쪽 끝 엘리먼트를 가져오는 동시에 데크에서는 삭제  
popleft() : 데크의 왼쪽 끝 엘리먼트를 가져오는 동시에 데크에서는 삭제   
extend(array) : 배열 array를 순환하면서 데크의 오른쪽에 추가  
extendleft(array) : 배열 array를 순환하면서 데크의 왼쪽에 추가    
remove(x) : x를 데크에서 찾아 삭제  
rotate(num) : 데크를 num만큼 회전 (양수면 오른쪽, 음수는 왼쪽으로)  

출처
https://cafecoder.tistory.com/44
https://velog.io/@nnnyeong/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0-%EC%8A%A4%ED%83%9D-Stack-%ED%81%90-Queue-%EB%8D%B1-Deque


----

# 📂 ArrayList란?
****
## 🔍 개념
- List 인터페이스를 상속받은 클래스로 크기가 가변적으로 변하는 선형리스트
- 순차리스트
- 객체들이 추가되어 저장 용량을 초과한다면 자동으로 부족한 크기만큼 저장 용량이 늘어남
- 일반적인 배열과 인덱스로 내부의 객체를 관리한다는 점이 유사 but, 인덱스는 한번 생성하면 크기 변하지 않음
- 추가, 삭제시 전체 객체의 위치가 움직임
- 잦은 원소의 이동에는 Linkedlist를 사용하는 것이 좋음
## 💻 사용법
  - import 필수
  ```
   import java.util.*
  ```
 - ArrayList 선언
    ```java
    ArrayList<item> my_items = new ArrayList<item>(); // 특정 객체(item)로 타입설정
    ArrayList<Integer> arr = new ArrayList<>();
    ArrayList<Integer> arr1 = new ArrayList<Integer>(); // int로 타입설정
    ArrayList<Integer> arr2 = new ArrayList<Integer>(10); // 10으로 용량 설정
    ```
- 메서드
  - 길이를 알려주는 메서드 : size()
    ```java
    ArrayList<Integer> list = new ArrayList<Integer>(Arrays.asList(1,2,3));
    System.out.println(list.size());
    ```
  - 추가하기 위한 메서드 : add(index,value)
    ```java
    ArrayList<Integer> list = new ArrayList<Integer>();
    list.add(1); //값 추가, index를 생략하면 맨 뒤에 추가
    list.add(null); //null값도 추가가능
    list.add(5,10); //index 5뒤에 10 삽입, 해당index부터 마지막 인덱스까지 1씩 밀림
    ```
  - 특정한 위치의 원소를 바꾸는 메서드 : set(index, 바꾸고 싶은 값)
       ```java 
       ArrayList<String> colors = new ArrayList<>();
        // add() method
        colors.add("Black");
        colors.add("White");
        colors.add(0, "Green");
        colors.add("Red");

        // set() method
        colors.set(0, "Blue");

        System.out.println(colors);
        ```
  - 삭제하기 위한 메서드 : remove()
    ```java
    ArrayList<Integer> list = new ArrayList<Integer>(Arrays.asList(1,2,3));
    list.remove(1);  //index 1 제거, 바로 뒤 인덱스부터 마지막까지 모두 앞으로 1씩 움직임
    list.clear();  //모든 값 제거
    ```
  - 값 존재 유무 : contains()
    ```java
    ArrayList<Integer> list = new ArrayList<Integer>(Arrays.asList(1,2,3));
    System.out.println(list.contains(1)); //list에 1이 있는지 검색 : true
    ```
  - 값이 있는 인덱스 출력 : indexOf(value)
    ```java
    ArrayList<Integer> list = new ArrayList<Integer>(Arrays.asList(1,2,3));
    System.out.println(list.indexOf(1)); //1이 있는 index반환 없으면 -1
    ```
  - 정렬 : sort()
    
    ```java
    ArrayList<Integer> list = new ArrayList<Integer>(Arrays.asList(1,2,3));
    Collections.sort(list);// Collections.sort() 메소드를 이용한 요소의 정렬
    ```


----
# 📂 LinkedList

## 🔍 개념
- 연결리스트라고도 불린다.
- 배열은 순차적으로 연결된 공간에 데이터를 나열하는 데이터 구조
- 링크드 리스트는 떨어진 곳에 존재하는 데이터를 화살표로 연결해서 관리하는 데이터 구조

### ⭕ 장점
- 데이터 공간을 미리 할당하지 않아도 됨. ( 배열은 미리 데이터 공간을 할당해야 함.)
### ❌ 단점
- 연결을 위한 별도 데이터 공간이 필요하므로, 저장공간 효율이 높지않음.
- 연결 정보를 찾는 시간이 필요하므로 접근 속도가 느림
- 중간 데이터 삭제 시, 앞 ▪ 뒤 데이터의 연결을 재구성해야하는 부가적인 작업 필요

> node : 데이터의 단위
> pointer : 각 노드안에서, 다음이나 이전 노드와의 연결 정보를 가지고 있는 공간

## 🗃️ 사용법
 - import 필수
   ```java
   import java.util.LinkedList;
   ```
 - 선언
   ```java
   LinkedList<Integer> numList = new LinkedList<Integer>();
   // LinkedList<>안에는 String등 다양한 데이터 타입을 선언할 수 있다.
   ```
 - 데이터 추가 메서드
   ```java
   numList.add(1);
   // → Linked List에 "()" 안에 데이터 값 추가.
   numList.add(1, 2);
   // → numList.add(인덱스번호, 데이터);
   numList.addFirst(1);
   // → Linked List 맨 앞에 "()" 안에 데이터를 추가
   numList.addLast(3);
   // → Linked List 맨 뒤에 "()" 안에 데이터를 추가
   ```
 - 데이터 삭제 메서드
   ```java
   umList.remove(2);
   // → Linked List "()" 안에 인덱스 번호에 해당되는 데이터를 삭제한다.
   numList.clear(); 
   // → Linked List엔아 모든 데이터를 삭제한다.
   ```
 - 링크드리스트 크기 구하는 메서드
   ```java
   System.out.println("size : " + numList.size());
   // → 현재 Linked List의 크기를 보여준다.
   ```
 - 데이터 출력하는 메서드
   ```java
   System.out.println(numList.get(1));
   // → "()"안에 인덱스번호에 해당되는 데이터를 출력한다.
   ```
 - 데이터 검색하는 메서드
   ```java
   System.out.println(numList.contains(1)); 
   // → 데이터 검색 (없으면 False 반환한다)
   System.out.println(numList.indexOf(1));
   // → 해당 데이터가 몇 번째 인덱스에 존재하는 지 확인 (없으면 -1 출력)
   ```
