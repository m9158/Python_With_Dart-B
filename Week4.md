# Python 4주차 정규 과제 

📌Python 정규과제는 매주 정해진 분량의 『*파이썬 라이브러리를 활용한 데이터 분석*』 을 읽고 학습하는 것입니다. 이번주는 아래의 **Python_4th_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 참고 자료를 통해 보완하는 것이 좋습니다.

**교재 실습 예제 파일은 07_Python_Template 레포지토리의 notebooks 폴더에 업로드되어 있습니다.**

**👀(수행 인증샷은 필수입니다.)** 

## Python_4th_TIL

### 5장 판다스 시작하기 
#### 1. 판다스 자료구조 소개
#### 2. 핵심 기능
#### 3. 기술 통계 계산과 요약
#### 4. 마치며 


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.25~82    | ✅         |
| 2주차 | p.83~129   | ✅         |
| 3주차 | p.131~179  | ✅         |
| 4주차 | p.181~246 | ✅         |
| 5주차 | p.247~309 | 🍽️         |
| 6주차 | p.310~379 | 🍽️         |
| 7주차 | p.381~465 | 🍽️         |


<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 학습 내용 정리

## 1. 판다스 자료구조 소개

### 개념정리

1. Series
   - 일련의 객체를 담을 수 있는 1차원 배열 같은 자료구조다.
   - 그리고 index라는 배열의 데이터와 연관된 이름을 갖는다.
   - Series의 배열과 색인 객체는 각각 array와 index 속성을 통해 얻을 수 있다.
   - 고정 길이의 정렬된 딕셔너리라고 생각하면 좋다.

2. DataFrame
   - 표 같은 스프레드시트 형식의 자료구조다.
   - 여러 개의 열이 있고 서로 다른 종류의 값을 담을 수 있다.
   - 행과 열에 대한 색인을 가지며, 색인의 모양이 같은 Series 객체를 담고 있는 파이썬 딕셔너리로 생각하면 좋다.
   - DataFrame의 색인은 Series와 동일한 방식으로 자동 할당되며 열은 data의 키 순서에 따라 정렬되어 저장된다.
   - head()를 통해 처음 5개행만 출력 가능. tail은 그 반대
   - 딕셔너리에 없는 값을 columns에 넘기면 결과에 결측치가 표시된다.
   - 리스트나 배열을 열에 대입할 때는 대입하려는 값의 길이가 DataFrame의 길이와 동일해야 한다.
   - del 예약어를 사용하여 열을 삭제할 수 있다.

3. 색인 객체
   - 축 레이블과 다른 메타데이터를 저장하는 객체다.
   - Series나 DataFrame 객체를 생성할 때 사용하는 배열이나 다른 순차적인 레이블은 내부적으로 색인으로 변환된다.
   - 색인 객체는 변경이 불가능 하다.
   - 파이썬 집합과 달리 판다스의 색인은 중복되는 값을 허용한다.


### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->


<img width="963" height="350" alt="image" src="https://github.com/user-attachments/assets/20bf3134-da95-4dfd-8151-e478681a1428" />

<img width="962" height="175" alt="image" src="https://github.com/user-attachments/assets/41838529-36eb-4e98-967e-d84902b9061d" />

~~~
Series
~~~

<img width="961" height="396" alt="image" src="https://github.com/user-attachments/assets/e36ed291-56f0-40e2-8cbf-664caccade27" />

<img width="960" height="426" alt="image" src="https://github.com/user-attachments/assets/786c9c29-17bc-4e1a-86f3-bee418b39f9f" />

<img width="958" height="446" alt="image" src="https://github.com/user-attachments/assets/358ee5e1-089b-4235-86cf-a3c154c09830" />

~~~
DataFrame
~~~

<img width="959" height="422" alt="image" src="https://github.com/user-attachments/assets/6e32fb55-968b-44bb-b262-bf6c75c21e30" />

~~~
색인 객체
~~~
## 2. 핵심 기능

### 개념정리

1. 재색인
   - reindex는 새로운 색인에 적합하도록 객체를 새로 생성하는 기능이다.
   - Series 객체에 대해서 reindex를 호출하면 데이터를 새로운 색인에 맞게 재배열하고, 존재하지 않는 색인값이 있다면 NaN을 새로 추가한다.

2. 하나의 행이나 열 삭제하기
   - 색인 배열을 갖고 있다면 reindex 메서드나 .loc 기반의 색인을 이용할 수 있으므로 행이나 열을 쉽게 삭제할 수 있다.
   - drop 메서드를 사용하면 선택한 값들이 삭제된 새로운 객체를 얻을 수 있다.

3. 색인하기, 선택하기, 거르기
   - Series의 색인은 넘파이 배열의 색인과 유사하게 작동하지만 정수가 아니어도 된다는 점이 다르다.
   - Series와 마찬가지로 DataFrame에는 레이블과 정수 기반 색인을 위한 loc, iloc 속성이 존재한다.
   - DataFrame은 2차원이므로 축 레이블(loc) 또는 정수 색인(iloc)을 이용해 행렬의 부분집합을 선택할 수 있다.

4. 산술 연산과 데이터 정렬
   - 판다스는 서로 다른 색인을 가지고 있는 객체 간의 산술 연산을 간단하게 처리할 수 있다.
   - 서로 겹치는 색인이 없는 경우 데이터는 결측치가 된다.
   - 공통 열이나 행 레이블이 없는 DataFrame을 더하면 결과는 아무것도 나타나지 않는다.
   - fill_value 값을 통해 누락된 값을 대체가 가능하다.
  
5. 함수 적용과 매핑
   - 판다스 객체에도 넘파이의 유니버설 함수를 적용할 수 있다.

6. 정렬과 순위
   - 정렬된 새로운 객체를 반환하는 sort_index 메서드를 사용해 행과 열의 색인을 알파벳순으로 정렬할 수 있다.
   - DataFrame은 행과 열 중 하나의 인덱스를 기준으로 정렬할 수 있다.
   - Series 객체를 값에 따라 정렬하고 싶다면 sort_values 메서드를 사용하면 된다.
   - 결측치는 맨 마지막에 위치한다.
   - rank 메서드는 동점인 항목에 대해서는 평균 순위를 매겨 책정한다.

7. 중복 색인
   - 색인은 유일해야 하지만 의무는 아니기에 중복된 색인을 가질 수 있다.
   - is_unique 속성은 해당 값이 유일한지 아닌지 알려준다.
   - 유일한 색인만 있다면 스칼라 값을 반환하고, 중복되는 색인값이 있을 때는 하나의 Seires 객체를 반환한다.

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->


<img width="964" height="337" alt="image" src="https://github.com/user-attachments/assets/0239f6d9-2f6c-4039-a976-bce18175a7e2" />

~~~
재색인
~~~

<img width="959" height="463" alt="image" src="https://github.com/user-attachments/assets/8eb2f062-6d60-4e70-b1f5-ea389156583c" />

~~~
하나의 행이나 열 삭제하기
~~~

<img width="961" height="407" alt="image" src="https://github.com/user-attachments/assets/fba89479-1a1f-4987-a8e9-742291081f71" />

<img width="964" height="457" alt="image" src="https://github.com/user-attachments/assets/ee1693bc-388e-4fea-8d95-0e2379285806" />

~~~
산술 연산과 데이터 정렬
~~~

<img width="961" height="252" alt="image" src="https://github.com/user-attachments/assets/1b83603d-f571-4cac-8099-c416391c4ebb" />

~~~
함수 적용과 매핑
~~~


<img width="958" height="280" alt="image" src="https://github.com/user-attachments/assets/19f156b3-c0f6-4cac-a7aa-ae0a6ea402c5" />

<img width="963" height="344" alt="image" src="https://github.com/user-attachments/assets/0acbcdf3-7c1b-4bd7-9439-c232477a1589" />

<img width="958" height="182" alt="image" src="https://github.com/user-attachments/assets/f8622b8c-eaf8-4c72-99b8-22f205219c8b" />


~~~
정렬과 순위
~~~


<img width="966" height="370" alt="image" src="https://github.com/user-attachments/assets/10cca307-9cd8-4b39-8d7a-c71a38de181f" />


~~~
중복 색인
~~~

## 3. 기술 통계 계산과 요약

### 개념정리

1. 기술 통계 계산과 요약
   - 판다스 객체는 일반적인 수학 메서드와 통계 메서드를 갖고 있다.
   - sum 메서드를 호출하면 각 열의 합을 담은 Series를 반환한다.
   - axis='columns' 또는 axis=1 옵션을 넘기면 각 열의 합을 반환한다.
   - 모든 값이 NA 값이라면 그 합은 0이 되고 값이 하나라도 NA라면 결과 값은 NA 다. 이는 skipna 옵션으로 비활성화 할 수 있다.
   - idxmin이나 idxmax 같은 메서드는 최소 혹은 최댓값을 가진 색인값 같은 간접 통계를 반환한다.
   - cumsum()으로 누산이 가능하다.

1-1. 상관관계와 공분산
   - corr 메서드는 NA가 아니며 정렬된 색인에서 연속하는 두 Series의 상관관계를 계산하고 cov 메서드는 공분산을 계산한다.
   - 반면 DataFrame에서 corr과 cov 메서드는 각 DataFrame 행렬상의 상관관계와 공분산을 계산한다.
   - corwith 메서드를 사용하면 다른 Series나 DataFrame과의 상관관계를 계산한다.

1-2. 유일값, 값 세기, 멤버십
   - unique 함수는 Series에서 중복되는 값을 제거하고 유일한 값만 담음 Series를 반환한다.
   - unique.sort()를 이용해서 유일값은 정렬된 순서로 반환한다.\
   - value.counts에서 반환하는 Series는 담고 있는 값을 내림차순 정렬한다.
   - isin 메서드는 어떤 값이 Series에 존재하는지 나타내는 불리언 벡터를 반환한다.

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="962" height="331" alt="image" src="https://github.com/user-attachments/assets/6d314a47-c976-4e58-9518-2a28af3923a1" />

<img width="962" height="450" alt="image" src="https://github.com/user-attachments/assets/20515df1-4ca4-458e-b51d-966165e1a60d" />

~~~
기술 통계 계산과 요약
~~~

<img width="958" height="417" alt="image" src="https://github.com/user-attachments/assets/909252a5-83f5-4933-a277-6d8cb6bca13b" />

<img width="961" height="262" alt="image" src="https://github.com/user-attachments/assets/d6e8a98f-11ff-46fc-b30d-cbdd2d117727" />

~~~
상관관계와 공분산
~~~

<img width="959" height="456" alt="image" src="https://github.com/user-attachments/assets/bfa83c67-5df0-48bb-a69b-2e6e575e2aa7" />

<img width="960" height="392" alt="image" src="https://github.com/user-attachments/assets/515d54df-f2d6-4253-9a84-1d9c15ff3ff6" />

~~~
유일값, 값 세기, 멤버십
~~~

# 2️⃣ 실습 과제

각 문제에 대한 실행 결과가 확인되도록 코드를 작성하고 실행한 뒤, **모든 문제의 실행 화면을 캡처하여 제출하시기 바랍니다.**

**1. 아래 코드를 실행하여 도서 매출 데이터를 생성합니다.**
```python
import pandas as pd
import numpy as np

# 도서 데이터 생성
data = {
    "book_name": ["Python 기초", "Pandas 실무", "데이터 분석", "머신러닝 입문", "딥러닝 가이드"],
    "price": [25000, 32000, 28000, 45000, 38000],
    "sales_count": [15, 8, 20, 5, 12],
    "stock": [10, 5, 0, 15, 7]
}
df = pd.DataFrame(data)
```

**2. 문제**
```
1. 데이터 확인 및 기초 통계 출력
  - 문제 설명: 요약 정보 확인 
  - describe() 메서드를 사용하여 수치형 데이터(가격, 판매량 등)의 기술 통계 정보를 출력하세요.
  - print()를 이용해 기술 통계 결과를 화면에 출력하세요.

2. 특정 조건의 데이터 필터링 (불리언 색인)
  - 문제 설명: 현재 재고가 하나도 없는(0인) 도서 찾기 
  - stock 열의 값이 0인 행만 추출하여 새로운 변수에 저장하세요.
  - print()를 이용해 재고가 0인 도서의 정보를 출력하세요.

3. 새로운 열 추가 (파생 변수 생성)
  - 문제 설명: 각 도서별 총 매출액(total_revenue) 계산
  - price와 sales_count를 곱하여 total_revenue라는 새로운 열을 추가하세요.
  - print()를 이용해 새로운 열이 추가된 DataFrame의 상단 5행(head)을 출력하세요.
```

<img width="954" height="400" alt="image" src="https://github.com/user-attachments/assets/c321220b-2939-4dea-8a6f-ecb1bd89cd64" />


<img width="960" height="327" alt="image" src="https://github.com/user-attachments/assets/4dc9fcc4-11b3-4308-b228-3e029ee04b0c" />


### 🎉 수고하셨습니다.







