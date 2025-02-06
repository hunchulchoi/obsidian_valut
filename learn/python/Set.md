## 집합의 특징

1. **중복 불허**: 동일한 요소를 여러 번 포함할 수 없습니다.
2. **순서 없음**: 요소들의 순서가 유지되지 않습니다.
3. **변경 가능(Mutable)**: 요소를 추가하거나 제거할 수 있습니다.
4. **해시 가능한 객체만 포함**: 리스트나 딕셔너리는 집합의 요소가 될 수 없습니다.

## 집합 생성

1. 중괄호 사용:
   ```python
   my_set = {1, 2, 3, 4, 5}
   ```

2. set() 생성자 사용:
   ```python
   my_set = set([1, 2, 3, 4, 5])
   ```

3. 빈 집합 생성:
   ```python
   empty_set = set()  # 주의: {}는 빈 딕셔너리를 생성합니다.
   ```

## 집합 연산

1. 요소 추가:
   ```python
   my_set.add(6)
   ```

2. 요소 제거:
   ```python
   my_set.remove(3)  # 요소가 없으면 KeyError 발생
   my_set.discard(3)  # 요소가 없어도 에러 발생하지 않음
   ```

3. 임의의 요소 제거 및 반환:
   ```python
   item = my_set.pop()
   ```

4. 모든 요소 제거:
   ```python
   my_set.clear()
   ```

## 집합 메서드

1. union(): 합집합
   ```python
   set1 = {1, 2, 3}
   set2 = {3, 4, 5}
   print(set1.union(set2))  # {1, 2, 3, 4, 5}
   ```

2. intersection(): 교집합
   ```python
   print(set1.intersection(set2))  # {3}
   ```

3. difference(): 차집합
   ```python
   print(set1.difference(set2))  # {1, 2}
   ```

4. symmetric_difference(): 대칭 차집합
   ```python
   print(set1.symmetric_difference(set2))  # {1, 2, 4, 5}
   ```

5. issubset(): 부분집합 여부 확인
   ```python
   print({1, 2}.issubset(set1))  # True
   ```

6. issuperset(): 상위집합 여부 확인
   ```python
   print(set1.issuperset({1, 2}))  # True
   ```

## 집합 연산자

- 합집합: `|`
- 교집합: `&`
- 차집합: `-`
- 대칭 차집합: `^`

```python
print(set1 | set2)  # {1, 2, 3, 4, 5}
print(set1 & set2)  # {3}
print(set1 - set2)  # {1, 2}
print(set1 ^ set2)  # {1, 2, 4, 5}
```

## 집합 컴프리헨션

```python
even_set = {x for x in range(10) if x % 2 == 0}
# {0, 2, 4, 6, 8}
```

>집합은 중복 제거, 멤버십 테스트, 수학적 집합 연산 등에 효율적으로 사용됩니다. 특히 고유한 요소들의 컬렉션이 필요하거나 빠른 멤버십 테스트가 필요한 경우에 유용합니다.
