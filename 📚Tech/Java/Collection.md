

![자바 컬렉션](https://blog.kakaocdn.net/dn/cGLOqE/btreAJdmGjw/K6PJ815H6m9KWTW9e42BD1/img.jpg)
[출처: https://choicode.tistory.com/25]( https://choicode.tistory.com/25)
## Collection

### List
- ArrayList : 쓰레드 안전하지 않다.
- Vector : 쓰레드 안전하다
- Stack : Vector를 상속한 클래스  
- LinkedList : 스택, 큐, 양방향 큐(Deque) 용도로 사용

### Set
- HashSet : 중복 저장할 수 없으며, **순서를 보장하지 않는다**. 내부적으로 `HashMap` 을 사용한다.
- LinkedHashSet : 중복 저장할 수 없지만 **입력한 순서대로 데이터를 정렬**한다. 내부적으로 `LinkedHashMap` 을 사용한다.
- TreeSet : 중복 저장할 수 없지만 . **오름차순으로 데이터를 정렬**하며 내부적으로 `TreeMap` 을 사용한다.
### Queue
- Priority Queue : 저장한 순서와 관계없이 우선순위가 높은 것부터 낸다.
- Deque  : Queue의 변형으로, 한쪽 끝으로만 추가/삭제 할 수 있는 큐와 달리 Deque 는 양쪽 끝에 추가/삭제가 가능하다.
	- LinkedList


## Map

### HashMap
### LinkedHashMap

### TreeMap
- 키를 정렬한다. 정렬되는 기본적인 순서는 아래와 같다. 아래 순서는 String 과 같은 문자열이 저장되는 순서이며 실제 숫자 또는 객체를 저장했을 때는 그 순서가 달라진다.
	- 숫자 > 알파벳 대문자 > 알파벳 소문자 > 한글 순이다. 


### HashMap vs Hashtable
- 키나 값에 null 가능여부 : O /  X
- 여러 쓰레드에서 안전 : X / O

왜 이러한 차이가 있을까? HashMap , TreeMap은  JDK1.2에서 추가되었고 LinkedHashMap 은 JDK 1.4에서 추가되었지만 Hashtable은 JDK 1.0부터 만들어져 사용된 클래스이고 Map 인터페이스 기능을 구현한거는 JDK1.2 부터이다.

**즉, 만들어진 Map 에 맞추어 보완되었다고 보면 된다.**

### HashMap 에서의 키가 되는 객체를 직접 생성할때의 유의점
HashMap 에 객체가 들어가면 hashCode() 메소드의 결과 값에 따른 버켓이라는 목록 형태의 바구니가 만들어진다. 서로 다른 키가 저장되었는데, hashCode() 결과값이 동일한 경우가 2개 이상인 경우 equals() 메소드를 통해 동일한 값을 찾는다. 

따라서 키가 되는 객체를 직접 작성할 때에는 hashCode() 와 equals() 메소드를 오버라이딩하여 작성을 잘하여야 한다.

> [!NOTE]
> hashCode() : 객체의 주소값을 변환하여 생성한 객체의 고유한 정수값을 리턴한다.



