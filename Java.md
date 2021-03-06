# Java
* [기본형과 참조형](#java-1)
* [객체지향 프로그래밍이란?](#java-2)
* [자바 컬렉션의 대표적인 인터페이스](#java-3)
* [접근 제어자의 종류와 특징](#java-4)
* [객체의 직렬화](#java-5)
* [쓰레드란?](#java-6)
* [static](#java-7)
* [클래스와 인스턴스](#java-8)
* [캡슐화와 상속](#java-9)
* [오버로딩과 오버라이딩](#java-10)
* [추상클래스와 인터페이스](#java-11)
* [변수의 종류와 선언위치](#java-12)
* [배열과 ArrayList의 차이](#java-13)
* [Java와 PHP의 차이점](#java-14)
* [Java, JSP, jQuery](#java-15)

## Primitive Type & Reference Type <a id="java-1" />
기본형은 논리형, 문자형, 정수형, 실수형 4가지 종류로 총 8개가 있고 계산을 위한 실제 값을 저장한다.
참조형은 기본형 8개를 제외한 나머지 타입, 객체의 주소를 저장한다.

## OOP란? <a id="java-2" />
클래스들 간에 서로 직접적인 관계를 맺어 줌으로써 유기적인 프로그래밍이 가능하다.
가장 큰 장점은 코드의 재사용성이 높고 유지보수가 용이하다는 점이다.<br>
특징은<br> 
1. 공통된 속성과 기능을 따로 분리하는 추상화
2. 조상타입으로 자손타입을 가리킬 수 있는 다형성
3. 메서드와 접근 제어자를 이용해 데이터를 보호하는 캡슐화
4. 조상클래스의 속성과 기능을 그대로 물려받을 수 있는 상속 

## 자바 컬렉션의 대표 인터페이스<a id="java-3" />
자바의 컬렉션은 다수의 데이터를 다루는데 표준화된 클래스들을 제공해주고 배열과 다르게 공간을 미리 할당할 필요가 없다.
대표적인 인터페이스로 List, Set, Map이 있다.

1. List<br>
  중복을 허용하고 저장순서를 유지한다는 특징이 있으며 구현한 클래스는 대표적으로 ArrayList, LinkedList, Stack 등이 있다.
2. Set<br>
  중복을 허용하지 않고, 저장순서를 유지하지 않는다. 구현한 클래스는 HashSet, 저장순서 유지하려면 LinkedHashSet 사용
3. Map<br>
  key-value 구조로 이루어져 있고, key는 중복이 허용되지 않고, value는 중복이 허용된다. 구현한 클래스는 HashMap이 있다.
4. Stack과 Queue<br>
  Stack은 List 인터페이스를 구현한 클래스이며 마지막에 저장한 데이터를 먼저 꺼내게되는 Last In First Out 구조 <br>
  Queue는 인터페이스이고 구현한 클래스는 LinkedList가 있다. 처음에 저장한 데이터를 먼저 꺼내게되는 First In First Out 구조
  
## 접근 제어자의 종류와 특징<a id="java-4" />
해당되는 멤버 또는 클래스를 접근할 수 있는 범위를 지정할 수 있다.
1. private : 같은 클래스 내에서 접근이 가능하다.
2. (default) : 같은 패키지 내에서 접근이 가능하다.
3. protected : 같은 패키지 및 다른 패키지의 자손클래스에서 접근이 가능하다.
4. public : 접근 제한이 없다.

## 객체의 직렬화<a id="java-5" />
객체에 저장된 데이터를 사용하기 위해 byte 형태의 스트림으로 만드는 것을 직렬화라 하고, 변환된 스트림을 다시 읽어서 객체를 만드는 것을 역직렬화라고 한다.

## 쓰레드란?<a id="java-6" />
- 프로세스 : 연속적으로 실행되고 있는 컴퓨터 프로그램
- 쓰레드 : 프로세스 내에서 실행되는 하나의 작업 단위이며 프로세스의 자원을 이용해서 실제로 작업을 처리한다.

자바에서 쓰레드를 구현하는 방법은 Thread 클래스를 상속받거나 Runnable 인터페이스를 구현하면 된다.

자바는 다중상속이 불가능하기 때문에 이미 상속을 받고있다면 Runnable 인터페이스를 구현한 후 run()메서드를 구현한 뒤 쓰레드 객체를 생성할때 생성자의 매개변수로 Runnable 인터페이스를 구현한 객채를 넘겨준다. -> start() 호출

Thread클래스를 상속받는 경우에는 run()메서드를 오버라이딩 한 뒤 자손클래스의 인스턴스를 생성한다. -> start() 호출

## static <a id="java-7" />
변수 또는 메서드앞에 붙는 키워드, 인스턴스를 생성하지 않고 사용할 수 있다.

모든 객체가 공통된 메모리영역을 공유한다.

클래스가 메모리에 올라갔을 때 생성되고 프로그램이 종료될 때 사라진다.

## 클래스와 인스턴스 <a id="java-8" />
클래스는 객체를 만들기 위해 존재하고 변수, 메서드 및 생성자로 구성되어있다.

인스턴스는 클래스에 정의된 것을 new 연산자를 통해 실제 메모리에 할당한 것으로 인스턴스마다 독립된 메모리 공간을 가질 수 있다.

## 캡슐화와 상속 <a id="java-9" />
캡슐화 : 객체의 속성과 기능을 하나로 묶고 외부에서 데이터에 직접 접근하지 못하게 접근 제어자와 메서드를 사용해 데이터를 보호한다.

상속 : 조상클래스의 속성과 기능을 그대로 물려받아 사용할 수 있고, 메서드를 자손 클래스에 맞춰서 변경해서 사용이 가능하다. 코드를 재사용할수 있고, 공통된 코드를 관리하기 때문에 유지보수가 용이하다.

## 오버로딩과 오버라이딩 <a id="java-10" />
오버로딩은 새로운 메서드를 정의하는 것(다양한 인자값을 매개변수로 받기 위해서), 반환타입과는 상관 없이 메서드의 이름이 동일하고, 매개변수의 타입이나 개수가 달라야한다.

오버라이딩은 조상클래스의 메서드를 자손클래스에 맞추어 적절히 변경해서 재정의하는것이고, 메서드의 선언부가 완전히 일치해야한다.

## 추상클래스와 인터페이스 <a id="java-11" />
추상클래스는 멤버변수, 메서드를 가질 수 있고, 추상 메서드가 포함되어있는 클래스이다. 키워드는 abstract를 사용하고 상속을 통해 추상메서드를 구현해야 한다.(기능확장)

인터페이스는 추상메서드와 상수, default, static 메서드를 가질 수 있다. 다른 클래스를 작성하는 데 도움을 줄 목적으로 작성된다. 다중 구현이 가능하고, implements 키워드를 사용해 구현한다.

## 변수의 종류와 선언위치 <a id="java-12" />
속성변수에는 인스턴스변수와 클래스변수가 있다. 모두 클래스 영역에서 생성되고, 인스턴스변수는 인스턴스를 생성해야 사용할 수 있고, 클래스변수는 인스턴스 생성없이 사용이 가능하다.

지역변수는 메서드 영역 내에서 생성되며 메서드가 끝나면 소멸되어 사용할 수 없다.

## 배열과 ArrayList의 차이? <a id="java-13" />
배열은 초기에 생성할때 길이가 정해지고, 기본형과 참조형 타입 모두 담을 수 있다.<br>
인덱스가 있어서 검색이 용이하고, 크기가 정해져 있기 때문에 데이터의 추가적인 삽입과 삭제가 자주 일어나지 않는다면 사용

list는 크기가 정해져 있지 않고, 추가적인 삽입이나 삭제가 자주 일어난다면 사용.<br>
제네릭을 이용해 타입을 지정할 수 있고, 기본형은(오토박싱)되고, 참조형 담을 수 있다.

### Java와 PHP의 차이점 <a id = "java-14" />
자바는 라이브러리가 풍부하고, 규칙이 있고, 체계적이며 프레임워크가 잘 갖춰져 있기 때문에 공공기관이나 대규모 프로젝트를 하는 기업에서 선호하고,

PHP는 자바처럼 컴파일이 필요하지 않는 스크립트 언어이기 때문에 서버를 재시작하지 않고 수정내용을 바로 바로 화면에서 볼 수 있다. 개발속도가 빠르다는 장점.

### Java, JSP, jQuery <a id = "java-15" />
JSP는 자바기반의 스크립트 언어이며, HTML 내에 자바코드를 삽입하여 서버에서 동적 웹 페이지를 생성해 클라이언트에게 돌려준다.
                         
jQuery는 Javascript의 라이브러리이고, 스크립트 언어를 단순화 할 수 있도록 설계되어있다.
                         
Java는 객체지향언어이고, 플랫폼에 독립적이며, 컴파일언어이다.
