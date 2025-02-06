## 딕셔너리의 특징

1. **키-값 쌍**: 각 항목은 키와 값의 쌍으로 구성됩니다.
2. **변경 가능(Mutable)**: 생성 후 내용을 수정할 수 있습니다.
3. **순서 있음(Python 3.7+)**: 항목들의 삽입 순서가 유지됩니다.
4. **키의 고유성**: 각 키는 유일해야 하며, 변경 불가능한 타입이어야 합니다.
5. **값의 다양성**: 값은 어떤 데이터 타입이든 가능합니다.

## 딕셔너리 생성

1. 중괄호 사용:
   ```python
   my_dict = {"apple": 1, "banana": 2, "cherry": 3}
   ```

2. dict() 생성자 사용:
   ```python
   my_dict = dict(apple=1, banana=2, cherry=3)
   ```

3. 리스트의 튜플로 생성:
   ```python
   my_dict = dict([("apple", 1), ("banana", 2), ("cherry", 3)])
   ```

## 딕셔너리 연산

1. 값 접근:
   ```python
   print(my_dict["apple"])  # 1
   ```

2. 값 수정:
   ```python
   my_dict["apple"] = 5
   ```

3. 새 항목 추가:
   ```python
   my_dict["date"] = 4
   ```

4. 항목 삭제:
   ```python
   del my_dict["banana"]
   ```

## 주요 딕셔너리 메서드

1. get(): 키로 값을 가져오며, 키가 없을 경우 기본값 반환
   ```python
   print(my_dict.get("fig", 0))  # 0
   ```

2. keys(): 모든 키를 반환
   ```python
   print(my_dict.keys())
   ```

3. values(): 모든 값을 반환
   ```python
   print(my_dict.values())
   ```

4. items(): 모든 (키, 값) 쌍을 튜플로 반환
   ```python
   print(my_dict.items())
   ```

5. update(): 다른 딕셔너리의 항목들을 추가
   ```python
   my_dict.update({"elderberry": 5, "fig": 6})
   ```

6. pop(): 지정된 키의 값을 반환하고 해당 항목 삭제
   ```python
   value = my_dict.pop("cherry")
   ```

## 딕셔너리 컴프리헨션

```python
squared = {x: x**2 for x in range(5)}
# {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

## 딕셔너리 순회

```python
for key, value in my_dict.items():
    print(f"{key}: {value}")
```

> 딕셔너리는 빠른 검색과 데이터 관리를 위한 강력한 자료구조로, 키를 통해 효율적으로 값에 접근할 수 있습니다. 특히 데이터의 구조화와 빠른 검색이 필요한 경우에 유용합니다.
