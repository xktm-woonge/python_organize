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

- ## DataFrame 활용

  - 