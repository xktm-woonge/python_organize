# ds_day7

## numpy

- 특징

```
넘파이 배열은 속도가 빠름, 적은 메모리 차지, 같은 자료형, 원소의 개수 변경 불가
리스트는 속도가 느림, 메모리 차지 많음, 자료형이 달라도 됨, 원소의 개수가 변경
```

- 차원

```
- 1차원 축(행) axis 0 -> Vector
- 2차원 축(열) axis 1 -> Matrix
- 3차원 축(채널) axis 2 -> Tensor(3차원이상)
```

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
     > - np.zeros | np.ones  -> 원소가 0or1인 배열을 생성(dtype을 통해 자료형 지정 가능)

  5. 난수 발생 함수

     > - np.random.seed() -> 기본 시드 지정 함수
     >
     > - np.random.randn() -> 표준 정규분포에 따른 n개의 무작위 숫자 생성
     >
     > - np.random.randint() -> 랜덤한 정수 생성
     >
     > - np.random.noraml(0,1,(n,n)) -> 평균이 0이고 표준편차가 1인 표준 정규를 띄는 배열

- 파이썬과 비교([1,2,3,4] -> [2,3,4,5] 전환)

> python(4번연산)
> ans=[]
> data=[1,2,3,4]
> for i in data:
>     ans.append(i+1)

```
[2, 3, 4, 5]
```

> numpy(1번연산)
> np.array(data)+1

```
[2, 3, 4, 5]
```

