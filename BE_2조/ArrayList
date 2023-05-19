### ArrayList란?
- List 인터페이스를 상속받은 클래스로 크기가 가변적으로 변하는 선형리스트
- 순차리스트
- 객체들이 추가되어 저장 용량을 초과한다면 자동으로 부족한 크기만큼 저장 용량이 늘어남
  - 일반적인 배열과 인덱스로 내부의 객체를 관리한다는 점이 유사 but, 인덱스는 한번 생성하면 크기 변하지 않음
- 추가, 삭제시 전체 객체의 위치가 움직임
- 잦은 원소의 이동에는 Linkedlist를 사용하는 것이 좋음
### 사용법
- import 필수
```java
import java.util.* 
```
- ArrayList 선언
```
    ArrayList<item> my_items = new ArrayList<item>(); // 특정 객체(item)로 타입설정
    ArrayList<Integer> arr = new ArrayList<>();
    ArrayList<Integer> arr1 = new ArrayList<Integer>(); // int로 타입설정
    ArrayList<Integer> arr2 = new ArrayList<Integer>(10); // 10으로 용량 설정
```
### 메서드
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
