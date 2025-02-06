* 정의
	* NotANumber
	* pandas에서 NaN 값은 비어있는 결측치 데이터를 의미한다.
	* 임의로 비어 있는 값을 대입 하고자 할 때는 numpy의 nan(np.nan)을 입력한다.
* 처리
	* 찾기
		* isnull(), isnan()
		* notnull(), notna()
	* 채우기
		* fillna()
* NaN 값이 있는 데이터 제거하기 
	* dropna()
		* how
			* any: default 
				* NaN이 한개라도 존재시 drop
			* all: 모두 NaN값이 존재시 drop
