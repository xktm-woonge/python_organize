# Numpy

- 특징

```
넘파이 배열은 속도가 빠름, 적은 메모리 차지, 같은 자료형, 원소의 개수 변경 불가
리스트는 속도가 느림, 메모리 차지 많음, 자료형이 달라도 됨, 원소의 개수가 변경
```

- 파이썬과 비교([1,2,3,4] -> [2,3,4,5] 전환)

  > python(4번연산)
  > ans=[]
  > data=[1,2,3,4]
  > for i in data:
  >  ans.append(i+1)

  ```
  [2, 3, 4, 5]
  ```

  > numpy(1번연산)
  > np.array(data)+1

  ```
  [2, 3, 4, 5]
  ```

  

- 차원

```
- 1차원 축(행) axis 0 -> Vector
- 2차원 축(열) axis 1 -> Matrix
- 3차원 축(채널) axis 2 -> Tensor(3차원이상)
```

- 스칼라 vs 벡터

  1. 스칼라

     >  방향은 없지만, 실수 공간에서 크기를 나타내는 값
     >
     > ex) 거리, 속도, 시각, 힘 에너지

  2. 벡터

     >  n차원 공간에서 방향과 크기를 갖는 단위
     >
     > ex) 배수량, 속도, 가속, 힘, 무게, 기세

- 연산

  ```
  x = np.array([[1, 2], [3, 4]], dtype=np.float64)
  y = np.array([[5, 6], [7, 8]], dtype=np.float64)
  ```

  - add(+)

    > print(x * y)
    >
    > print(np.multiply(x, y))
    >
    > ```
    > [[ 5. 12.]
    > [21. 32.]]
    > ```

  - subtrack(-)

    > print(x - y)
    >
    > print(np.subtract(x, y))
    >
    > ```
    > [[-4. -4.]
    > [-4. -4.]]
    > ```

  - multiply(*)

    > print(x * y)
    >
    > print(np.multiply(x, y))
    >
    > ```
    > [[ 5. 12.]
    > [21. 32.]]
    > ```

  - divide( / )

    > print(x / y)
    >
    > print(np.divide(x, y))
    >
    > ```
    > [[0.2        0.33333333]
    > [0.42857143 0.5       ]]
    > ```

  - sqrt(제곱근)

    > print(np.sqrt(x))
    >
    > ```
    > [[1.         1.41421356]
    > [1.73205081 2.        ]]
    > ```

  - dot(@(벡터의 내적, 벡터와 행렬의 곱))

    > print(x.dot(y))
    >
    > print(np.dot(x, y))
    >
    > ```
    > [[19 22]
    > [43 50]]
    > ```

- 함수

  1. array구조 파악 함수

     > - array.dtype -> 데이터의 자료형 반환
     >
     > - array.shape -> 몇행 몇열로 이루어져 있는지 반환
     > - array.ndim -> 차원의 크기 반환
     > - array.size -> 원소의 개수 반환
     > - array.reshape -> 주어진 배열의 형태를 바꿀때 사용

  2. 통계값 구하는 함수

     > - np.sum() -> 배열의 합계
     > - np.average() -> 배열의 평균
     > - np.median() -> 중앙값
     > - np.var() -> 분산
     > - np.std() -> 표준편차
     > - np.max() -> 최대값
     > - np.min() -> 최소값

  3. 빈도수와 탐색

     > - np.bincount() -> 배열의 0부터 최댓값까지 정렬한 뒤 각 원소에 대한 빈도수 반환
     > - np. agrmax() -> 배열의 최대 값 위치 반환
     > - np.agrmin() -> 배열의 최소 값 위치 반환

  4. array 생성 함수

     > - np.arrange() -> 지정된 범위의 숫자를 원소 값으로 하는 배열 생성
     >
     > - np.zeros | np.ones  -> 원소가 0or1인 배열을 생성(dtype을 통해 자료형 지정 가능)
     >
     > - np.linspace() -> 균일한 간격으로 데이터 생성
     >
     >   > array = np.linspace(0, 10, 5)
     >   >
     >   > print(array)
     >
     >   ```
     >   [ 0.   2.5  5.   7.5 10. ]
     >   ```

  5. 난수 발생 함수

     > - np.random.seed() -> 기본 시드 지정 함수
     >
     > - np.random.randn() -> 표준 정규분포에 따른 n개의 무작위 숫자 생성
     >
     > - np.random.randint() -> 랜덤한 정수 생성
     >
     > - np.random.noraml(0,1,(n,n)) -> 평균이 0이고 표준편차가 1인 표준 정규를 띄는 배열

  



- ​	인덱싱

  > 파이썬과 동일하게 참조 가능
  >
  > - 배열[양수, 음수, 0]으로 참조 가능 
  >
  > - 다차원 배열 참조시
  >
  > - 변수[행, 열]로 참조

- 배열 합치기

  1. Concatenate 함수

     > arr1 = np.array([[1, 2],
     >
     > ​								[3, 4]]) 
     >
     > arr2 = np.array([[5, 6],                  
     >
     > ​								[7, 8]]) 
     >
     > arr3 = np.concatenate((arr1, arr2), axis=0) 
     >
     > ※axis =0 or 1 ==> 0은 세로축, 1은 가로축
     >
     >  print(arr3)
     >
     > ```
     > [[1 2]
     > [3 4]
     > [5 6]
     > [7 8]]
     > ```
     >
     > 

  2. stack 함수

     - stack 계열 함수 : 행 또는 열의 수가 동일한 두 개 이상의 배열을 연결

       > arr1 = np.array([1, 2, 3]) 
       >
       > arr2 = np.array([4, 5, 6]) 
       >
       > arr3 = np.stack((arr1, arr2), axis=0) 
       >
       > print(arr3)
       >
       > ```
       > [[1 2 3]
       > [4 5 6]]
       > ```
       >
       > arr4 = np.stack((arr1, arr2), axis=1) 
       >
       > print(arr4)
       >
       > ```
       > [[1 4]
       > [2 5]
       > [3 6]]
       > ```

     - hstack : 행의 개수가 동일한 배열을 옆으로 연결

       > x1=np.ones((2,3)) # 행 2, 열 3
       >
       > x2=np.zeros((2,2))# 행 2, 열 3
       >
       > np.hstack([x1,x2])
       >
       > ```
       > array([[1., 1., 1., 0., 0.],
       >        [1., 1., 1., 0., 0.]])
       > ```
       >
       > 

     - vstack: 열의 개수가 동일한 배열을 밑으로 연결

       > x3=np.ones((2,3)) # 행 2, 열 3
       >
       > x4=np.zeros((3,3))# 행 3, 열 3
       >
       > np.vstack([x3,x4])
       >
       > ```
       > array([[1., 1., 1.],
       >        [1., 1., 1.],
       >        [0., 0., 0.],
       >        [0., 0., 0.],
       >        [0., 0., 0.]])
       > ```

