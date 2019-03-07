# 파이썬 기본 문법 공부하기
### 01. 시작하기 (3/2)
- python3 설치
- Visual Studio

### 02. 데이터 타입 (3/2)
- '==' or '!=' 는 '값'을 비교할 때 사용
- 'is' or 'is not' 참조 비교, 객체 비교할 때 사용

### 03. 기본 자료 구조(3/4)
- Container(list, set, dict, tuple, str): 여러 원소들을 가지고 있는 자료 구조
- Container 자료구조 모두 in 연산자로 멤버쉽 테스트 지원
- dict 순회시, key 목록만 순회 -> value 순회를 원한다면, .values() 함수 이용

### 04. 블록문, 들여쓰기, 주석 (3/5)
- `#`~은 python이 처리하지 않지만, 주석으로도 사용하는 '~'/'''~'''/"~"/"""~"""은 python이 문자열로 처리
- PEP(Python Enhancements Proposals)

### 05. 흐름 제어 (3/5)

### 06. 함수 (3/5)
- 전역 변수: 파이썬에서는 주로 '상수(Constant)' 목적으로 많이 사용, 따로 상수 문법 없음(const, val 등)
- 변수의 값이 변경되는 경우 -> 그 유효 범위를 최소화 / 지역변수 사용이 버그 발생확률을 획기적으로 낮출 수 있음
- Arguments
1. Positional Arguments 
2.Keyword Arguments
- Packing: 인자의 갯수를 제한하지 않고, 다수의 인자를 받을 수 있음, Positional Arguments를 하나의 tuple로 받을 수 있음
- Unpacking: Sequence Data Type(리스트/튜플 등)을 다수의 인자인 것처럼 나누어 함수에 전달 가능
- 클래스를 상속할 시, 부모의 멤버 함수를 오버라이딩할 때 가변인자 정의가 유용
- 익명함수(Anonymous Function): lambda식(=간편하게 쓰는 한 줄 함수)을 통해 익명함수 생성                   
- 1급 객체: 다른 객체들에 적용 가능한 연산을 모두 지원하는 객체 ex) 일급함수/클래스/컨트롤 등
- 고차함수(High Order Function): 다른 함수를 생산/소비하는 함수 (= 다른 함수를 인자로 받거나, 그 결과로 함수를 반환하는 함수)

### 07. 클래스 (3/5)
- Object Oriented Programming(OOP): 큰 문제를 작게 쪼개는 것이 아니라, 먼저 작은 문제들을 해결할 수 있는 객체들을 생성한 뒤, 이 객체들을 조합해서 큰 문제를 해결하는 상향식(Bottom-up) 해결법을 도입
- OOP 주요 특징 
1. 캡슐화(Encapsulation) 
2. 상속(Inheritance) 
3. 다향성(Polymorphism)
- 다향성(Polymorphism): 프로그래밍 언어의 자료형 체계의 성질을 나타내는 것으로, 프로그램 언어의 각 요소들(상수, 변수, 식, 오브젝트, 함수, 메소드 등)이 다양한 자료형(type)에 속하는 것이 허가되는 성질을 가리킨다. 반댓말은 단형성(Monomorphism)으로, 프로그램 언어의 각 요소가 한가지 형태만 가지는 성질을 가리킨다.
- 클래스(Class): 사용자 정의 데이터 타입, 관련된 다수의 변수와 함수의 묶음으로 구성
- Tip: 파이썬에서 함수명은 snake_case, 클래스명은 CamelCase
- 클래스 없이 함수로도 구현 가능한 기능/동작을 클래스로 구현한다면, 훨씬 응집도 있는 처리가 가능
- 생성자(Constructor): 클래스가 호출될 때, 클래스 내 __int__ 함수가 자동 호출, 이 함수를 생성자라 하며 인스턴스를 초기화하는 역할, 클래스 호출 시 넘겨진 인자는 모두 생성자의 인자로 넘겨짐

### 08. 호출 가능한 객체 (3/5)
- 함수 호출, 클래스 호출: Python에서 기본 지원 o
- 인스턴스 호출: Python에서 기본 지원 x -> 따라서, 직접 구현해야함
- __call__: 인스턴스를 호출 가능토록 만들어주는 멤버 함수
- 인스턴스를 호출 가능하도록 만드는 것이 유리할 경우
1. 상태값을 유지하는 함수
2. 기존 함수와 비슷한 로직의 함수를 만드는 경우(클래스 상속을 통한 중복 제거 후, __call__멤버 함수를 통해 마치 함수를 호출 하는 것처럼 구현)

### 09. 순회 가능한 객체 (3/6)
- iterable: 순회 가능한 객체 / set, list, dict, tuple, string, generator
- Generator: 값을 생산해내는 객체
  - generator expression
  - generator function

### 10. 코루틴 및 제너레이터 (3/6)
- python2 -> range와 xrange 개념이 구분
- python3 -> range이 xrange로 변경

- Co-Routine(코루틴)
 - 진입점이 여럿이며, 병렬(Concurrensy, not Parallelism)
 - 호출부와 함수는 대등한 관계
 - 여러번 호출이 되어도, Routine 내 Context가 유지
 
- Generator
 - getnerator은 항상 iterator
 - 연속된(Swquence)값들을 생산해내는 함수
 - 함수에 yield한 값들이 순차적으로 생산
 - Generator에서 return 문을 만나더라도 종료만 될 뿐, 리턴값이 사용되지 않는다. Generator은 오직 yield를 통해서만 값을 리턴
 - 추가 yield가 없으면, Stoplteration 예외 자동 발생 (for 루프는 StopIteration 예외를 자동으로 처리)
 - 중첩된 Fenerator은 Pipline 작동

### 11. 빌트인 함수, 정렬 (3/6)
- sorted: 정렬된 리스트를 반환
- sorted_list = sorted(iterable, key=None, reverse=False)

- list의 sort 멤버함수: list는 자체적으로 sort함수를 지원
 - list자체의 순서를 변경
 - sorted와 다르게 리턴값이 없다. 즉, None을 리턴한다.

- filter: 지정 함수로 필터링된 결과를 생산할 Iterator를 반환, 각 원소마다 지정함수가 호출되어, 리턴값이 True 판정될 경우 통과
- iterator = filter(필터링 여부를 결정할 함수, iterable)

- map: 지정 함수의 리턴값을 반환할 Iterator 반환
- iterator = map(값을 변환할 함수, iterable)

- max/min: iterable에서 key함수를 거친 결과값 중에 가장 큰 결과값의 반환
- Tip: max와 min을 사용할 떄는 default값을 정해주는 것이 좋다.
