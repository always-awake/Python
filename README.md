# 파이썬 기본 문법 공부하기
### 01. 시작하기
- python3 설치
- Visual Studio

### 02. 데이터 타입 
- '==' or '!=' 는 '값'을 비교할 때 사용
- 'is' or 'is not' 참조 비교, 객체 비교할 때 사용

### 03. 기본 자료 구조
- Container(list, set, dict, tuple, str): 여러 원소들을 가지고 있는 자료 구조
- Container 자료구조 모두 in 연산자로 멤버쉽 테스트 지원
- dict 순회시, key 목록만 순회 -> value 순회를 원한다면, .values() 함수 이용

### 04. 블록문, 들여쓰기, 주석
- `#`~은 python이 처리하지 않지만, 주석으로도 사용하는 '~'/'''~'''/"~"/"""~"""은 python이 문자열로 처리
- PEP(Python Enhancements Proposals)

### 05. 흐름 제어

### 06. 함수
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

### 07. 클래스 
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

### 08. 호출 가능한 객체
- 함수 호출, 클래스 호출: Python에서 기본 지원 o
- 인스턴스 호출: Python에서 기본 지원 x -> 따라서, 직접 구현해야함
- __call__: 인스턴스를 호출 가능토록 만들어주는 멤버 함수
- 인스턴스를 호출 가능하도록 만드는 것이 유리할 경우
1. 상태값을 유지하는 함수
2. 기존 함수와 비슷한 로직의 함수를 만드는 경우(클래스 상속을 통한 중복 제거 후, __call__멤버 함수를 통해 마치 함수를 호출 하는 것처럼 구현)

### 09. 순회 가능한 객체 
- iterable: 순회 가능한 객체 / set, list, dict, tuple, string, generator
- Generator: 값을 생산해내는 객체
  - generator expression
  - generator function

### 10. 코루틴 및 제너레이터 
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

### 11. 빌트인 함수, 정렬 
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
  
### 12. 모듈 패키지 
- import 다른 파이선 소스파일 내 함수/클래스 등을 현재의 공간으로 가져오기
- import 시점에서 해당 코드 실행
- 모듈(modules): 다수의 함수/클래스들을 정의해둔 파이썬 소스코드 파일
- 패키지(apckages): 파이썬 소스코드가 들어있는 디렉토리, 해당 디렉토리에는 __init__ 파일이 있어야, 파이썬 팩키지로 인식됨
- 팩키지를 import 할 때에는 __init__.py 가 import 대상
- Tip: 모듈명/패키지명을 지정할 때, Python의 Built_in 라이브러리명과 겹치지 않도록 하기
- 파이썬 소스코드 내 __name__
  - 최초 진입(파이썬쉘에서 파일명.py으로 실행) 소스코드일 경우: "__main__" 으로 변경되어 실행
  - import 된 소스코드일 경우: 본래 __name__ 이 유지된 채로 실행

### 13. 문자열 인코딩 
- Character Encoding(문자 인코딩): 문자나 기호들의 집합을 부호화(인코딩)하는 방법
  - 변환하는 방법: ascii, cp949, utf-8 등
  - 변환하는 행위
- python2: unicode/str
- python3: str/byte
- 파이썬에서의 인코딩: 유니코드 문자열(str 타입) -> 인코딩 -> byte 타입 문자열
- 파이썬에서의 디코딩: byte 타입 문자열 -> 디코딩 -> 유니코드 문자열(str 타입)
- Unicode(유니코드): 기존 인코딩의 한계를 극복하고, 전 세계의 모든 문자를 일관되게 표현할 수 있도록 설계된 산업 표준
- UTF-8: 모든 유니코드 문자 표현 가능, 가변 길이 문자 인코딩 방식(1바이트 ~ 4바이트)
- Tip: 파이썬 코드 안에서는 모두 디코딩 하여, 유니코드로 처리 -> 유니코드로 문자열을 처리하면, 한글 처리에 불편함이 없다. 글자수 세기도 쉽다.

### 14.파일에 저장하고 읽어오기 
- 데이터를 영속성있게 저장할려면 파일에 저장해야함
  - 파이썬에서는 open 함수를 통해 파일 읽기/쓰기 지원
- TEXT: 문자열데이터
  - 유니코드로 관리
  - 유니코드를 인코딩 후 파일에 저장
  - 문자열만 자동 인코딩/디코딩(python3에서만 지원, python2에서는 수동 인코딩/디코딩 필요)이 의미가 있음
- BINARY: 바이너리 데이터
  - 자동 인코딩/디코딩 수행 x -> raw data 그대로 read
- open(파일 쓰기/읽기 함수)
```
file_obj = open(파일경로, mode='rt', encoding=None [, 그외 옵션 생략])
readed_data =file_obj.read()
file_obj.close()
```
  
### 15. 오버로딩과 오버라이딩 
- 오버로딩(Overloading): 이름은 같지만, 인자와 리턴타입이 다른 멤버 함수를 여럿 정의하는 것(파이썬에서는 미지원)
- 오버 라이딩(Overriding): 클래스 상속에서 사용되는 개념, 상위 클래스가 갖고 있는 메소드를 하위 클래스가 재정의
- 클래스 주요 오버라이딩 멤버 함수(부모 클래스의 함수를 자식 클래스가 재정의)
  - __init__(self[,...]) : 생성자 함수
  - __repr__(self): 시스템이 해당 객체를 인식할 수 있는 Official 문자열, 대개 디버깅을 위해 사용
  - __str__(self): Informal 문자열. str(obj)시에 호출됨.
  - __getitem__(self, key): self[key] 구현
  - __setitem__(self, key, value): self[key] = value
- 연산자 재정의 가능 -> 자주 사용 x
- with절 지원

### 16. 클래스 상속과 MRO
- 코드 중복을 최소화하기 위한 목적으로 등장
- 파이선 클래스는 최상위 클래스인 object 상속 (파이썬3에서는 old-style class 제거)
- 파이썬은 다중상속 지원: 직계 부모가 다수
- MRO(Method Resolution Order)
  - 파이썬의 클래스 탐색순서는 MRO(=클래스 상속 순서)를 따름 -> Class.mro()를 MRO확인 가능
  - MRO가 꼬이도록 클래스를 설계할 수 없음 -> TypeError 발생
- 부모의 함수 호출
  - 내장함수 super()을 통해 부모의 함수 호출 가능
  - super 호출 시에 MRO에 기반하여 호출해야함

### 17. 예외 처리 
- 프로그램이 처리되는 동안 특정한 문제(예외)가 일어났을 때 진행중인 루틴을 중단하고, 콜스택을 거슬러 올라가, 예외를 전파하는 메커니즘
- try - except 문으로 예외를 잡아 처리할 수 있음 -> 진행중인 루틴이 중단되지 않고 이어서 계속 실행됨 (예외를 정확히 잡아 처리했다면)
- 호출한 함수 내에서 발행한 예외도 잡을 수 있음
- tuple로 예외를 다수 지정할 수 있음
- as를 통해 예외 인스턴스 획등 가능
- else: 예외가 발생하지 않았을 때 호출되는 블럭
- finally: 예외 발생 유무에 상관없이 호출되는 블럭

### 18. 장식자 - 끝
- 어떤 함수를 감싸는 (Wrapping) 목적의 함수
- 1급함수: 함수를 동적으로 생성 가능, 반환값으로 전달 가능
- 장식자에 인자 지원 가능
