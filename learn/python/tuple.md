## 튜플의 특징
1. **불변성(Immutable)**: 생성 후 내용을 변경할 수 없습니다.
2. **순서가 있는 컬렉션**: 인덱싱과 슬라이싱이 가능합니다.
3. **중복 허용**: 동일한 값을 여러 번 포함할 수 있습니다.
4. **다양한 데이터 타입 저장**: 숫자, 문자열, 불리언 등 여러 타입을 함께 저장할 수 있습니다.
## 튜플 생성

1. 소괄호 사용:
   ```python
   my_tuple = (1, 2, 3, "apple", True)
   ```

2. 소괄호 없이 생성 (패킹):
   ```python
   my_tuple = 1, 2, 3, "apple", True
   ```

3. tuple() 생성자 사용:
   ```python
   my_tuple = tuple([1, 2, 3])
   ```

## 튜플 연산

1. 인덱싱:
   ```python
   print(my_tuple[0])  # 1
   ```

2. 슬라이싱:
   ```python
   print(my_tuple[1:3])  # (2, 3)
   ```

3. 결합 (concatenation):
   ```python
   tuple1 = (1, 2)
   tuple2 = (3, 4)
   combined = tuple1 + tuple2  # (1, 2, 3, 4)
   ```

4. 반복:
   ```python
   repeated = (1, 2) * 3  # (1, 2, 1, 2, 1, 2)
   ```

## 튜플 메서드

튜플은 불변이므로 메서드가 제한적입니다:

1. count(): 특정 값의 개수 반환
   ```python
   my_tuple = (1, 2, 2, 3)
   print(my_tuple.count(2))  # 2
   ```

2. index(): 특정 값의 첫 번째 인덱스 반환
   ```python
   print(my_tuple.index(2))  # 1
   ```

## 튜플 언패킹

```python
a, b, c = (1, 2, 3)
print(a, b, c)  # 1 2 3
```

## 튜플의 활용

1. 함수에서 여러 값 반환:
   ```python
   def get_coordinates():
       return (10, 20)

   x, y = get_coordinates()
   ```

2. 딕셔너리 키로 사용:
   ```python
   dict_with_tuple = {(1, 2): "value"}
   ```

3. 데이터 보호:
   중요한 데이터를 변경하지 않도록 보호할 때 사용합니다.

> 튜플은 불변성으로 인해 리스트보다 메모리 효율적이며, 데이터 무결성이 중요한 경우에 유용합니다.