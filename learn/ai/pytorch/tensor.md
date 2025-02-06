### 개요
- 배열이나 행렬과 매우 유사한 특수한 자료구조
- pytorch에서는 tensor를 사용하여 모델의 입력과 출력, 모델의 매개변수를 부호화(encode)한다.
- GPU나 다른 하드웨어의 가속기에서 실행할수 있다는 점만 제외하면 ndarray와 유사
- 
### 초기화
#### 데이터로 부터 직접(directly) 생성
- 데이터로부터 직접 텐서를 생성할 수 있습니다. 데이터의 자료형(data type)은 자동으로 유추합니다.
```python
data = [[1, 2],[3, 4]]

x_data = torch.tensor(data)

# tensor([[1, 2], [3, 4]])
```
#### NumPy 배열로부터 생성하기
- 텐서는 NumPy 배열로 생성할 수 있습니다. (그 반대도 가능합니다 - `bridge-to-np-label` 참고)
```python
np_array = np.array(data)

x_np = torch.from_numpy(np_array)

# tensor([[1, 2], [3, 4]])
```
#### 다른 텐서로부터 생성하기
- 명시적으로 재정의(override)하지 않는다면, 인자로 주어진 텐서의 속성(모양(shape), 자료형(datatype))을 유지합니다.
```python
x_ones = torch.ones_like(x_data) # x_data의 속성을 유지합니다.

print(f"Ones Tensor: \n {x_ones} \n")

# Ones Tensor: tensor([[1, 1], [1, 1]]) Random Tensor: 

x_rand = torch.rand_like(x_data, dtype=torch.float) # x_data의 속성을 덮어씁니다.

print(f"Random Tensor: \n {x_rand} \n")

# tensor([[0.6057, 0.8385], [0.6275, 0.3812]])
```
#### 무작위(random) 또는 상수(constant) 값을 사용하기
- ``shape`` 은 텐서의 차원(dimension)을 나타내는 튜플(tuple)로, 아래 함수들에서는 출력 텐서의 차원을 결정합니다.
```python
shape = (2,3,)

rand_tensor = torch.rand(shape)

ones_tensor = torch.ones(shape)

zeros_tensor = torch.zeros(shape)
  

print(f"Random Tensor: \n {rand_tensor} \n")

print(f"Ones Tensor: \n {ones_tensor} \n")

print(f"Zeros Tensor: \n {zeros_tensor}")
```
### 속성(Attribute)
- 모양(`shape`)
- 자료형(`datatype`)
- 어느 장치에 저장되는 지(`device`)
```python
ensor = torch.rand(3,4)

print(f"Shape of tensor: {tensor.shape}")
print(f"Datatype of tensor: {tensor.dtype}")
print(f"Device tensor is stored on: {tensor.device}")

print(tensor)

"""
Shape of tensor: torch.Size([3, 4]) 
Datatype of tensor: torch.float32 
Device tensor is stored on: cpu 
tensor([[0.7391, 0.6469, 0.5864, 0.4591], [0.2248, 0.1322, 0.3522, 0.7884], [0.5962, 0.0245, 0.4843, 0.8266]])
"""
```
### 연산(Operation)
- 전치(transposing)
- 인덱싱(indexing)
- 슬라이싱(slicing)
- 수학 계산
- 선형 대수
- 임의 샘플링
-  각 연산들은 (일반적으로 CPU보다 빠른) GPU에서 실행할 수 있습니다.
- ``.to`` 메소드를 사용하면 (GPU의 가용성(availability)을 확인한 뒤) GPU로 텐서를 명시적으로 이동할 수 있습니다. 장치들 간에 큰 텐서들을 복사하는 것은 시간과 메모리 측면에서 비용이 많이든다는 것을 기억하세요!
```python
# GPU가 존재하면 텐서를 이동합니다

if torch.cuda.is_available():
	tensor = tensor.to("cuda")

if torch.backends.mps.is_available():
	tensor = tensor.to("mps")

print('torch.cuda.is_available()', torch.cuda.is_available())

print('torch.backends.mps.is_available()', torch.backends.mps.is_available())

print('torch.backends.mps.is_built()', torch.backends.mps.is_built())
```
#### tensor 합치기(`cat`)
#### 단일-요소(single-element) 텐서
#### 바꿔치기(in-place) 연산
- 연산결과를 피연산자(operand)에 저장하는 연산
- `_` 접미사를 갖는다.
```python
# 더하기
tensor.add_(value)

# 빼기
tensor.sub_(value)

# 곱하기
tensor.mul_(value)

# 나누기
tensor.div_(value)

# 복사
tensor.copy_(source)
```
#### Numpy 변환
##### tensor -> numpy
```python
t = torch.ones(5)
print(f"t: {t}")

n = t.numpy()
print(f"n: {n}")
```
##### numpy -> tensor
```python
n = np.ones(5)

t = torch.from_numpy(n)
```
