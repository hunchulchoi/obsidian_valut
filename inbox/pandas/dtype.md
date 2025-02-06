## category
* category 타입으로 변경시 메모리 사용량 감소
* category 컬럼은 df[컬럼].cat으로 접근하여 category attribute 사용 가능
* 변경
	* df[컬럼].cat.categories = [...]
		* 원래 순서에 맞출것
## datetime
* https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DatetimeIndex.year.html*
* .dt로 datetime attribute에 접근 가능
* 변경
	* pd.to_datetime(df[])
