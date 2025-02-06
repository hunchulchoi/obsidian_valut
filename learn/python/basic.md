Python의 기초 문법을 정리해 드리겠습니다. 주요 개념과 구문들을 포함하여 다양한 측면을 다루겠습니다.

### 1. 변수와 데이터 타입
- **변수 선언**: Python은 동적 타이핑 언어이므로 변수 타입을 명시적으로 선언할 필요가 없습니다.
  ```python
  x = 10          # 정수
  y = 3.14        # 부동소수점
  name = "Alice"  # 문자열
  is_active = True  # 불리언
  ```

- **데이터 타입**:
  - **정수**: `int`
  - **부동소수점**: `float`
  - **문자열**: `str`
  - **불리언**: `bool`
  - **리스트**: `list`
    - 순서가 있고, 변경 가능한 시퀀스
    - 대괄호 `[]`로 표현
  - **튜플**: `tuple`
    - 순서가 있고, 변경 불가능한 시퀀스
    - 소괄호 `()`로 표현
    - 읽기 전용 리스트와 유사
    - 패킹과 언패킹 지원
  - **딕셔너리**: `dict`
    - 키-값 쌍으로 이루어진 순서 있는 컬렉션 (Python 3.7+)
    - 중괄호 `{}`로 표현
    - 키는 고유하고 변경 불가능해야 함
    - 주요 메서드: keys(), values(), items(), get()
  - **집합**: `set`
    - 순서가 없고, 중복을 허용하지 않는 컬렉션
	•	중괄호 `{}`로 표현 (빈 집합은 set())
	•	수학적 집합 연산 지원 (합집합, 교집합, 차집합 등)
	•	주요 메서드: add(), remove(), union(), intersection()
-  **데크** `Deque`
	•	collections 모듈의 양방향 큐
	•	양쪽 끝에서 빠른 삽입과 삭제 지원
	•	주요 메서드: append(), appendleft(), pop(), popleft()
### 2. 기본 연산자
- **산술 연산자**: `+`, `-`, `*`, `/`, `//` (정수 나눗셈), `%` (나머지), `**` (제곱)
  ```python
  a = 10
  b = 3
  print(a + b)       # 덧셈
  print(a * b)       # 곱셈
  print(a / b)       # 나눗셈
  print(a % b)       # 나머지
  print(a ** b)      # 제곱
  ```

- **비교 연산자**: `==`, `!=`, `>`, `<`, `>=`, `<=`
  ```python
  x = 5
  y = 10
  print(x == y)     # 같음
  print(x != y)     # 다름
  print(x < y)      # 작음
  ```

- **논리 연산자**: `and`, `or`, `not`
  ```python
  a = True
  b = False
  print(a and b)    # 논리 AND
  print(a or b)     # 논리 OR
  print(not a)      # 논리 NOT
  ```

### 3. 제어 구조
- **if-else 문**:
  ```python
  age = 20
  if age >= 18:
      print("성인입니다.")
  else:
      print("미성년자입니다.")
  ```

- **for 루프**:
  ```python
  for i in range(5):
      print(i)
  ```

- **while 루프**:
  ```python
  count = 0
  while count < 5:
      print(count)
      count += 1
  ```

### 4. 함수 정의와 호출
- **함수 정의**:
  ```python
  def greet(name):
      return f"Hello, {name}!"

  message = greet("Alice")
  print(message)
  ```

- **함수 인자와 반환값**:
  - **기본 인자값**:
    ```python
    def greet(name="Guest"):
        return f"Hello, {name}!"

    print(greet())       # 기본값 사용
    print(greet("Bob"))  # 인자 전달
    ```

  - **다중 반환값**: 튜플을 사용하여 여러 값을 반환할 수 있습니다.
    ```python
    def get_coordinates():
        return 10, 20

    x, y = get_coordinates()
    print(x, y)
    ```

### 5. 리스트와 딕셔너리
- **리스트**:
  ```python
  numbers = [1, 2, 3, 4, 5]
  numbers.append(6)  # 추가
  numbers.remove(3)  # 제거
  print(numbers)
  ```

- **딕셔너리**:
  ```python
  person = {"name": "Alice", "age": 25}
  person["city"] = "New York"  # 새로운 키-값 추가
  print(person["name"])        # 키에 대한 값 접근
  ```

### 6. 클래스와 객체 지향 프로그래밍
- **클래스 정의**:
  ```python
  class Person:
      def __init__(self, name, age):
          self.name = name
          self.age = age

      def introduce(self):
          return f"{self.name}, {self.age}세"

  alice = Person("Alice", 25)
  print(alice.introduce())
  ```

### 관련 노트 검색 (@vault)
더 자세한 내용이나 특정 주제에 대한 예시를 찾고 싶으시다면 다음과 같은 노트를 찾아볼 수 있습니다:
- [[Python 변수와 데이터 타입]]
- [[Python 제어 구조]]
- [[Python 함수 정의와 사용]]
- [[Python 리스트와 딕셔너리 활용]]
- [[Python 클래스와 객체 지향 프로그래밍]]

특정 주제나 예제에 대해 더 자세히 알고 싶으시다면 알려주세요!