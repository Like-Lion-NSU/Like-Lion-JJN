## deque (Double Ended Queue)

1. 데크의 정의
</br>
- Double ended :양 끝이 닮은, 양 끝이 앞이 되는 , 앞 뒤가 없는 의  뜻
</br>
 즉, depue는 양 끝이 앞 뒤가 되는 큐이다.
- depue 는 스택과 큐의 특징을 모두 가진다. ( FIFO 이지만 양쪽에서 들어오고 나갈 수 있음.)
</br>

ex) 터널과 비슷한 구조를 가질 수 있음. 터널은 양쪽으로 들어갈수도 나갈 수도 있기때문 !
</br>
cf. depue 의 파생으로 스크롤과 셸프가 존재
</br>
- 스크롤 : 입력이 한쪽 끝으로만 가능 (입력 제한)
- 셸프 : 출력이 한쪽 끝으로만 가능(출력제한)
</br>
![img_2.png](img_2.png)

#### 특징 
- 데이터를 양쪽에서 삽입 한 곳에서는 삭제가 가능한 구조

- 데이터 입력 순서와 상관없이 출력 순서 조절 가능

- 스택과 큐의 장점을 모아서 만들어진 자료구조
 - deque는 list보다 속도가 빠르고, 쓰레드 환경에서 안전하기 때문이다.

pop(0)와 같은 메서드를 수행할 때 리스트의 경우 O(N)연산을 수행하지만 deque는 O(1) 연산을 수행한다.

따라서, push와 pop이 빈번한 알고리즘의 경우, list보다 deque를 사용하는것이 효율적이며 속도가 더 빠르다.
### deque의 구조

- 앞부분은 front 마지막은 last로 표현
- push는 push_front(),push_back()
- pop은 pop_front(), pop_back()

![img.png](img.png)
-  사진에서 데큐의 중간 지점을 mid 라고 한다.
- 첫 시작은 front와 last 모두 mid 에서 시작함
- front나 Last의 위치가 같으면 mid로 초기화 시켜주기!
- 큐가 가득 찬 상태로 데이터가 들어오면 정렬을 실행함.
- 모든 원소를  한칸씩 밀어 공간을 만들어줌

- 사용법

| 사용           | 내용                                                                                                    |
|--------------|-------------------------------------------------------------------------------------------------------|
| push_front() | 첫 입력 X<br/>1.--Front;<br/>2.Array[front] = data;  <br/>첫 입력 <br/>1.Array[Front] = data;<br/>2.++Last; |
| push_Last()  | 첫 입력 X<br/>1.--Last;<br/>2.Array[Last] = data;<br/> 첫 입력 <br/>1.Array[Last] = data;<br/>2.--front;    |
| pop_front()  | 1.Array[front] =null<br/>2.++front;                                                                   |
| pop_Last()   | 1.Array[Last] =null<br/>2.--Last;                                                                     |


### depue 메서드
데이터 전체 획득/ 비어있는지 확인: Deque.getBuffer(), Deque.isEmpty()
데이터 추가/삭제: Deque.pushFront(), Deque.popFront(), Deque.pushBack(), Deque.popBack()
첫번째 & 끝 데이터 반환/사이즈/ 전체삭제: Deque.front(), Deque.back(), Deque.size(), Deque.clear()
deque.append(x) : x를 데크의 오른쪽 끝에 삽입한다

deque.appendleft(x) : x를 데크의 왼쪽 끝에 삽입한다

deque.pop() : 데크의 오른쪽 끝 엘리먼트를 가져오는 동시에 데크에서는 삭제한다

deque.popleft() : 데크의 왼쪽 끝 엘리먼트를 가져오는 동시에 데크에서는 삭제한다

deque.extend(array) : 배열 array를 순환하면서 데크의 오른쪽에 추가한다

deque.extendleft(array) : 배열 array를 순환하면서 데크의 왼쪽에 추가한다

deque.remove(x) : x를 데크에서 찾아 삭제한다

deque.rotate(num) : 데크를 num만큼 회전한다 (양수면 오른쪽, 음수는 왼쪽으로)

### 구현 소스
```agsl
// Deque(): 초기 속성값 설정을 위한 생성자 함수
function Deque(array = []) {
  this.array = array;
}

// getBuffer(): 객체 내 데이터 셋 반환
Deque.prototype.getBuffer = function () {
  return this.array.slice();
};

// isEmpty(): 데이터 비어 있는지 확인
Deque.prototype.isEmpty = function () {
  return this.array.length === 0;
};

// pushFront(): 앞쪽 데이터 추가
Deque.prototype.pushFront = function (element) {
  return this.array.unshift(element);
};

// popFront(): 앞쪽 데이터 삭제
Deque.prototype.popFront = function () {
  return this.array.shift();
};

// pushBack(): 뒤쪽 데이터 추가
Deque.prototype.pushBack = function (element) {
  return this.array.push(element);
};

// popBack(): 뒤쪽 데이터 삭제
Deque.prototype.popBack = function () {
  return this.array.pop();
};

// front(): 가장 첫 데이터 반환
Deque.prototype.front = function () {
  return this.array.length === 0 ? undefined : this.array[0];
};

// back(): 가장 끝 데이터 번환
Deque.prototype.back = function () {
  return this.array.length === 0
    ? undefined
    : this.array[this.array.length - 1];
};

// size(): 큐 내 데이터 개수 확인
Deque.prototype.size = function () {
  return this.array.length;
};

// clear(): 큐 초기화
Deque.prototype.clear = function () {
  this.array = [];
};

let dq = new Deque([1, 2, 3]);
console.log(dq);

console.log(dq.front());
console.log(dq.back());
console.log(dq.size());

dq.clear();
console.log(dq);
```