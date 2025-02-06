>Pandas는 데이터 과학, 머신러닝, 금융 분석 등 다양한 분야에서 널리 사용되며, 효율적인 데이터 처리와 분석을 가능하게 합니다.
## 주요 데이터 구조
1. Series: 1차원 레이블된 배열
2. DataFrame: 2차원 레이블된 데이터 구조 (표 형식)

## DataFrame 생성

```python
import pandas as pd

# 딕셔너리로부터 생성
df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})

# CSV 파일로부터 생성
df = pd.read_csv('file.csv')
```

## 데이터 조회
- head(), tail(): 처음/마지막 n개 행 조회
- info(): DataFrame 정보 요약
- describe(): 수치형 열의 통계 요약

## 데이터 선택
- 열 선택: df['column_name'] 또는 df.column_name
- 행 선택: df.loc['label'] 또는 df.iloc[index]
- 조건부 선택: df[df['column'] > value]

## 데이터 처리
- 결측치 처리: dropna(), fillna()
- 중복 제거: drop_duplicates()
- 데이터 타입 변환: astype()
- 열 이름 변경: rename()
## 데이터 집계 및 그룹화
- groupby(): 데이터 그룹화
- agg(): 여러 집계 함수 적용
- pivot_table(): 피벗 테이블 생성

## 데이터 병합
- merge(): SQL 조인과 유사한 데이터 병합
- concat(): 데이터프레임 연결
## 시계열 데이터 처리
- to_datetime(): 문자열을 날짜/시간으로 변환
- resample(): 시계열 데이터 리샘플링

## 데이터 입출력
- read_csv(), to_csv(): CSV 파일 읽기/쓰기
- read_excel(), to_excel(): Excel 파일 읽기/쓰기
- read_sql(), to_sql(): SQL 데이터베이스 읽기/쓰기