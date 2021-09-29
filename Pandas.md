# Pandas

```
파이썬에서 사용하는 데이터분석 라이브러리
행과 열로 이루어진 데이러 객체를 만드어 다룰 수 있고 안정적으로 대용량 데이터 처리 가능
```

- ## 자료구조

  - Series

    - Series 정의하기

      > object = pd.Series([1, 2, 3, 4])
      >
      > print(object)
      >
      > ```
      > 0    1
      > 1    2
      > 2    3
      > 3    4
      > dtype: int64
      > ```

    - Series 값 확인

      > print(object.values)
      >
      > ```
      > array([1, 2, 3, 4], dtype=int64)
      > ```

    - Series 인덱스 확인

      > print(object.index)
      >
      > ```
      > RangeIndex(start=0, stop=4, step=1)
      > ```

    - Series 자료형 확인

      > print(object.dtypes)
      >
      > ```
      > dtype('int64')
      > ```

    - Series 인덱스 설정및 바꾸기

      > object1 = pd.Series([1, 2, 3, 4], index=['a','b','c','d'])
      >
      > print(object1)
      >
      > object1 = pd.Series([1, 2, 3, 4])
      >
      > object1.index = ['a','b','c','d']
      >
      > print(object1)
      >
      > ```
      > a    1
      > b    2
      > c    3
      > d    4
      > dtype: int64
      > ```

    - python dictionary -> Series 전환

      > data = ['a':1, 'b':2,'c':3,'d':4]
      >
      > object2 = pd.Series(data)
      >
      > ```
      > a    1
      > b    2
      > c    3
      > d    4
      > dtype: int64
      > ```

  - Data Frame

    - Data Frame 만들기

      > data = {'name': ['Kim', 'Park', 'Lee', 'choi', 'Park'],
      >
      > ​    'year': [1997, 1998, 1997, 1999, 2000],
      >
      > ​    'month': [7, 6, 12, 1, 2]}
      >
      > df = pd.DataFrame(data)
      >
      > df
      
      ![캡처111](md-images/%EC%BA%A1%EC%B2%98111.PNG)
      
      

    - 행 방향 index

      > df.index
      >
      > ```
      > RangeIndex(start=0, stop=5, step=1)
      > ```
      >
      > 

    - 열 방향 index

      > df.columns
      >
      > ```
      > Index(['name', 'year', 'month'], dtype='object')
      > ```
      >
      > 

    - 행, 열 index에 대한 이름 설정

      > df.index.name= 'ind'
      >
      > df.columns.name = 'col'
      >
      > df
      >
      > ![캡처222](md-images/%EC%BA%A1%EC%B2%98222.PNG)

    - DataFrame 만들며 columns, index 이름 정하기

      > df2 = pd.DataFrame(data, columns=['year', 'name', 'month', 'day'],
      >
      > ​         index=['first', 'second', 'third', 'fourth', 'fifth'])
      >
      > df2
      >
      > ![캡처3333](md-images/%EC%BA%A1%EC%B2%983333.PNG)

    - describe

      1. 통계량은 Series에 대해 요약

      2. DataFrame의 경우 열에 대해 요약

      3. 누락데이터 제외 요약

         > df2.describe()
         >
         > ![캡처4444](md-images/%EC%BA%A1%EC%B2%984444-1632827504515.PNG)

- ## DataFrame 함수

  - 결측치 관련 함수

    - isna(), isnull() -> data값이 결측값이면 True, 아니면 False 반환
    - notna(),notnull() -> data값이 결측값이 아니면  True, 맞으면 False 반환 
    - fillna(), replace(), interpolate() -> 결측값을  대체하거나 채울 때 사용
    - dropna() -> 결측값 제거

  - data 읽거나 불러오기

    - read_csv()
    - read_excel()
    - read_html()

  - 인덱스, 라벨

    - df.iloc[행, 열] -> 행이나 칼럼의 순서를 나타내는 정수로 특정 값 추출
    - df.loc[행 , 열] -> 사람이 읽을 수 있는 라벨값으로 특정 값 추출

  - 그 외

    - drop -> 행 또는 열 제거
    - value_counts() -> 컬럼에 있는 벨류값들의 갯수를 더해 반환
    - sort_index (axis=축, ascending=True(오름차순)|False(내림차순), inplace=Ture(제자리)) -> index 축 기준으로 정렬
    - sort_values (by=정렬기준, ascending=True(오름차순)|False(내림차순), inplace=Ture(제자리)) -> values 정렬기준으로 정렬

  - pivot

    - 데이터 테이블 재배치

    - 여러 column을 index, values, columns 값으로 사용

      > data.pivot(index=None, columns = None, values = None)
      >
      > - index : index 만드는 열
      > - columns : columns 만드는 열
      > - values : 채워질 값

  - pivot_table

    - 요약된 정보 출력

      > data.pivot_table(values=None, index=None, columns=None, aggfunc='mean', fill_value=None, margins=False, dropna=True, margins_name='All')
      >
      > - values : 집계할 data
      >
      > - index : data와 같은 길이의  배열
      > - columns : data와 같은 길이의 컬럼 
      > - aggfunc : data 축약시 사용할 함수
      > - margins : 행/ 열 병합

  - GroupBy

    - 데이터를 그룹별로 나누어 확인할 때 사용

      > df3=df2.groupby(['year','name']).sum()
      >
      > df3
      >
      > ![캡처7777](md-images/%EC%BA%A1%EC%B2%987777.PNG)