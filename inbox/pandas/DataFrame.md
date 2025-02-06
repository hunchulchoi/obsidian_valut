## 정의
* 2차원 데이터 구조
* 행(row), 열(column) 으로 구성
* 각 column은 각각의 데이터 타입 (dtype)을 가진다.
## 생성
* ``pd.DataFrame()``
		* 2차원 list, Dictionary
		* columns=[]
## 속성
* columns
* values
* dtypes
* T
		* dataframe을 전치(Transpose)
* index
	* df.index = list('abc')
	* reset_index 
		* 인덱스 초기화
* column
	* column 명 변경
		* df.rename(columns={}, inplace=True)
* type변경
	* df[].astype('str')
## 빈도
* value_counts()
	* sort 
		* 빈도순으로 정렬 default=True
	* normailize 
		* 비율로 표시 default=False
## 조건 필터
### loc
* indexing과 slicing을 할수 있다.
* [i] slicing은 [시작[포함]: 끝[포함]]
* df.loc[index, columns]
### iloc
* loc과 비슷하지만 index만 허용
## 통계
### describe() - 요약통계
* 수치형 컬럼에 대한 통계표를 보여줌  
	* count  
	* mean  
	* std  
	* min  
	* max
* 문자형 요약 통계
	* include=‘object’
		- count
		- unique
		- top
		- freq : 가장 많이 출연한 데이터 빈도수
### count()
### mean() - 평균
* skipna=True
	* 기본으로 설정되어 있음
	* False일 경우 NaN갑이 있는 column은 NaN으로 출력
## 복사 copy
* df.copy()
* 복제한 dataframe을 수정해도 **원본에는 영향을 미지치 않음**
## 전처리
### 추가
* 임의의 값을 대입해 새로운 컬럼을 추가
	* df['temp'] = True
* insert
	* 중간에 컬럼을 추가하고 싶은 경우
	* insert(컬럼인덱스, 컬럼명, 값)
### 삭제
* drop()
	* 원본에 바로 삭제되는 것은 아니다.
	* 변수에 재대입하여 결과를 반영하거나 **inplace=True** 옵션
* row
	* 행 삭제시 index를 지정하여 삭제
* column
	* 열 삭제시 **axis=1** 옵션을 지정
### 연산
* 컬럼간 연산 
	* df['a'] + df['b']
		* 문자열 합치기도 가능
	* 소수점 자리수 지정
		* round(df['a']/df['b'], 2)
	* 숫자 연산 시 NaN값이 있다면 결과는 NaN
### 구간나누기 
#### cut
* 연속된 수치(continuous values)를 구간으로 나누어 카테고리화 할때 사용
* pd.cut(컬럼, [구간(bin)])
* attribute
	* right=False 
		* 우측 볌위를 포함하지 않음
	* labels
		* 지정한 bins의 개수보다 1개가 적어야 한다
	* bins
		* 나누고자 하는 구간의 개수를 입력
#### qcut
* 동일한 갯수를 갖도록 구간 분할
* 범위를 지정할 수 있다.
* attribute
	* q=3
		* 나누고자 하는 갯수
	*  labels=
		* 구간에 나타낼 라벨
	* precision
		* default 3
		* 3인 경우 소수점 3자리까지
## 함수적용
* apply
* 함수를 컬럼 혹은 DataFrame에 적용
## groupby
*  df.groupby([컬럼]).aggregate함수
* df.groupby([컬럼]).[컬럼]aggregate함수
* 여러개의 통계 함수를 적용할때는 .agg([통계함수])를 적용
## pivot table
* pivot과 pivot_table 차이점
	* pivot table은 중복되는 모호한 값이 있을 경우, aggregation 함수 사용하여 값을 채움
* 엑셀의 pivot table, pandas의 groupby와 비슷하다.
* 기본적으로 index, column, values를 지정하여 피벗한다.
![[Pasted image 20240101203523.png]]
![[Pasted image 20240101203805.png]]
![[Pasted image 20240101203827.png]]
![[Pasted image 20240101204053.png]]

## 연결 concat
* concat은 2개 이상의 dataframe을 행 혹은 열 방향으로 연결
* pd.concat([df])
* attribute
	* ignore_index
		* 인덱스를 무시하고 연결(새로 생성)
### 행방향으로 연결
* 기본값인 axis=0이 지정되어 있고, 행방향으로 연결
* 같은 column을 찾아서 데이터를 연결한다.
* 일부 컬럼이 누랃되거나 순서가 바뀌어도 알아서 같은 컬럼끼리 병합
### 열방향으로 연결
* axis=1
* 같은 index끼리 연결된다.
## 병합 merge
* 서로 다른 구성이지만 공통된 key값(컬럼)을 가지고 있다면 병합할 수 있다.]
* pd.merge(df1, df2)
* how
	* left
	* right
	* outer
	* **inner**
