Python에서 리스트는 데이터를 순서대로 저장하고 관리할 수 있는 기본적인 자료형입니다. 리스트의 주요 특징과 사용법은 다음과 같습니다:

---
## **리스트의 특징**
1. **순서가 있는 데이터 구조**: 리스트는 데이터가 추가된 순서를 유지합니다.
2. **변경 가능(Mutable)**: 리스트의 내용을 수정, 추가, 삭제할 수 있습니다.
3. **중복 허용**: 동일한 값을 여러 번 포함할 수 있습니다.
4. **다양한 데이터 타입 지원**: 숫자, 문자열, 불리언 등 다양한 데이터 타입을 한 리스트에 포함할 수 있습니다.

---
## **리스트 생성**
1. 대괄호(`[]`)를 사용:
   ```python
   my_list = [1, 2, 3, "apple", True]
   ```

2. `list()` 생성자 사용:
   ```python
   empty_list = list()
   range_list = list(range(5))  # [0, 1, 2, 3, 4]
   ```

---
## **리스트 주요 메소드**
1. **추가**
   - `append()`: 리스트 끝에 요소 추가
     ```python
     my_list.append("banana")
     ```
   - `insert()`: 특정 위치에 요소 추가
     ```python
     my_list.insert(1, "orange")
     ```
   - `extend()`: 다른 리스트나 반복 가능한 객체를 병합
     ```python
     my_list.extend([4, 5])
     ```

2. **삭제**
   - `remove()`: 특정 값을 삭제 (첫 번째로 발견된 값만 삭제)
     ```python
     my_list.remove("apple")
     ```
   - `pop()`: 특정 인덱스 값을 반환하며 삭제 (인덱스 없으면 마지막 값)
     ```python
     last_item = my_list.pop()
     ```
   - `clear()`: 모든 요소 삭제
     ```python
     my_list.clear()
     ```

3. **정렬 및 순서 변경**
   - `sort()`: 오름차순 정렬 (기본값), 내림차순은 `reverse=True` 사용
     ```python
     my_list.sort(reverse=True)
     ```
   - `reverse()`: 리스트를 역순으로 뒤집음
     ```python
     my_list.reverse()
     ```

4. **검색 및 개수 세기**
   - `index()`: 특정 값의 첫 번째 인덱스 반환
     ```python
     idx = my_list.index("banana")
     ```
   - `count()`: 특정 값의 개수 반환
     ```python
     cnt = my_list.count("apple")
     ```

---
## **리스트 슬라이싱(Slicing)**
- 부분 리스트를 추출:
  ```python
  sub_list = my_list[1:4]  # 인덱스 1부터 3까지 추출 (4는 제외)
  ```
- 간격 설정:
  ```python
  sub_list = my_list[::2]  # 두 칸씩 건너뛰며 추출
  ```

---
## **리스트 컴프리헨션(List Comprehension)**
- 간결하게 리스트 생성:
  ```python
  squares = [x**2 for x in range(5)]  # [0, 1, 4, 9, 16]
  even_numbers = [x for x in range(10) if x % 2 == 0]  # [0, 2, 4, 6, 8]
  ```

---
## **예제 코드**
```python
# 리스트 생성 및 기본 연산
fruits = ["apple", "banana", "cherry"]
fruits.append("mango")         # ['apple', 'banana', 'cherry', 'mango']
fruits.remove("banana")        # ['apple', 'cherry', 'mango']
fruits.sort(reverse=True)      # ['mango', 'cherry', 'apple']
print(fruits[0])               # mango

# 리스트 컴프리헨션 예제
numbers = [x for x in range(10) if x % 2 == 0]  
print(numbers)                 # [0, 2, 4, 6, 8]
```

---

Python 리스트는 유연성과 강력한 기능을 제공하며 데이터 분석부터 웹 개발까지 다양한 분야에서 널리 사용됩니다!
