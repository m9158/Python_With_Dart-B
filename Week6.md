# Python 6주차 정규 과제 

📌Python 정규과제는 매주 정해진 분량의 『*파이썬 라이브러리를 활용한 데이터 분석*』 을 읽고 학습하는 것입니다. 이번주는 아래의 **Python_6th_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 참고 자료를 통해 보완하는 것이 좋습니다.

**교재 실습 예제 파일은 07_Python_Template 레포지토리의 notebooks 폴더에 업로드되어 있습니다.**

**👀(수행 인증샷은 필수입니다.)** 

## Python_6th_TIL

### 7장 데이터 정제 및 준비 
#### 3. 확장 데이터 유형
#### 4. 문자열 다루기 
#### 5. 범주형 데이터
#### 6. 마치며
### 8장 데이터 준비하기: 조인, 병합, 변형
#### 1. 계층적 색인
#### 2. 데이터 합치기 
#### 3. 재구성과 피벗
#### 4. 마치며 


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.25~82    | ✅         |
| 2주차 | p.83~129   | ✅         |
| 3주차 | p.131~179  | ✅         |
| 4주차 | p.181~246 | ✅         |
| 5주차 | p.247~309 | ✅         |
| 6주차 | p.310~379 | ✅         |
| 7주차 | p.381~465 | 🍽️         |


<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 학습 내용 정리

## 1. 확장 데이터 유형

### 개념정리

- 넘파이 한계
  - 정수/불리언 + 결측치 → 자동으로 float64 변환
  - 대량 문자열 데이터 → 계산 비용↑, 메모리↑
  - 일부 타입은 파이썬 객체 사용 → 속도 느림
    
- 해결: 판다스 확장 dtype
  - 결측값은 np.nan 아닌 pd.NA 사용
  - 핵심 타입: Int64, boolean, string, Float64, category
  - astype()으로 변환 가능

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="963" height="442" alt="image" src="https://github.com/user-attachments/assets/60d78341-ddf3-4196-ab01-bb16ccf4a9ba" />


<img width="960" height="177" alt="image" src="https://github.com/user-attachments/assets/8ddaaa82-936a-49fd-aa4c-c3baa688a6c1" />


## 2. 문자열 다루기 

### 개념정리

- 파이썬 내장 문자열 메서드
  - split : 구분자로 분리 / strip : 공백 제거 / join : 합치기
  - find : 위치 반환(-1 if 없음) / index : 위치 반환(없으면 예외)
  - count : 등장 횟수 / replace : 치환

- 정규 표현식 (re 모듈)
  - findall : 일치하는 모든 패턴 리스트 반환
  - search : 첫 번째 매칭만 반환 (위치 포함)
  - match : 문자열 시작부터만 검사
  - sub : 패턴을 다른 문자열로 치환
  - re.compile() : 정규식 객체로 만들어 재사용 → CPU 절약

- 판다스 str 접근자
  - NA 값 자동 처리 + 벡터화 연산
  - str.contains, str.findall, str.extract, str.get, str[:]

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="963" height="484" alt="image" src="https://github.com/user-attachments/assets/b55d6ae1-e509-4f42-baec-f42c3cc62fc3" />
<img width="959" height="399" alt="image" src="https://github.com/user-attachments/assets/653a207d-0921-4da2-ad3d-dab7443f593c" />

<img width="953" height="427" alt="image" src="https://github.com/user-attachments/assets/24d830b5-0c3b-4773-ac1d-51c463bd3930" />
<img width="967" height="384" alt="image" src="https://github.com/user-attachments/assets/2a770b99-d982-46f2-bacb-6a99ff6ebcc1" />
<img width="962" height="243" alt="image" src="https://github.com/user-attachments/assets/693918df-59b8-4623-8ada-af0dc39f34fd" />

## 3. 범주형 데이터

### 개념정리

- 개념
  - 반복값을 정수 코드로 저장 → 메모리↓, 속도↑
  - pd.unique() / pd.value_counts() 로 고유값/빈도 확인
  - dim.take(values) : 정수 코드로 원래 문자열 복원

- 핵심 속성/메서드
  - .astype('category') : 범주형 변환
  - .cat.codes : 정수 코드 / .cat.categories : 고유 범주 목록
  - ordered=True : 순서 있는 범주형 (foo < bar < baz)
  - .cat.set_categories() : 범주 추가
  - .cat.remove_unused_categories() : 안 쓰는 범주 제거
  - pd.get_dummies() : 원-핫 인코딩(더미 변수)

- 성능: 문자열 배열 대비 value_counts() 약 30배 빠름, 메모리 약 60분의 1

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->


<img width="957" height="455" alt="image" src="https://github.com/user-attachments/assets/6d8988eb-8309-4d82-97cd-ddc18528c4dd" />
<img width="966" height="485" alt="image" src="https://github.com/user-attachments/assets/4269c030-3025-417b-8e0a-d570918614b6" />
<img width="960" height="477" alt="image" src="https://github.com/user-attachments/assets/371d51e2-1786-4163-98d5-3792ab339852" />
<img width="956" height="369" alt="image" src="https://github.com/user-attachments/assets/f76e1e09-49a5-4a7a-b799-0d533df8bf0e" />


## 4. 계층적 색인 

### 개념정리

- 개념
  - 하나의 축에 2개 이상 색인 단계 → MultiIndex
  - 고차원 데이터를 2D로 표현 가능
  - 부분 색인(Partial indexing)으로 하위 그룹 선택 가능

- 핵심 메서드
  - unstack() : 내부 색인 → 열 / stack() : 열 → 내부 색인
  - swaplevel() : 레벨 순서 교환 (데이터 변경 없음)
  - sort_index(level=) : 레벨 기준 정렬
  - set_index() / reset_index() : 열↔색인 전환
  - groupby(level=) : 계층별 집계

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="953" height="416" alt="image" src="https://github.com/user-attachments/assets/fba8f207-dd0d-4084-a203-f0fa0ff7f447" />
<img width="957" height="455" alt="image" src="https://github.com/user-attachments/assets/66394955-fe3f-4169-a929-eac5946f0481" />
<img width="961" height="362" alt="image" src="https://github.com/user-attachments/assets/9cf50852-3e32-478f-8992-e1a100f70bee" />
<img width="958" height="305" alt="image" src="https://github.com/user-attachments/assets/d3b48e4e-797b-4ec4-a4c7-960597515f1c" />
<img width="961" height="385" alt="image" src="https://github.com/user-attachments/assets/238a3770-ecaf-453a-8c8e-eef946a39be8" />
<img width="957" height="184" alt="image" src="https://github.com/user-attachments/assets/ad1748f5-95bb-4041-b12f-e51cfb6142e6" />


## 5. 데이터 합치기 

### 개념정리

- pd.merge(): 공통 키 기준 조인
  - how: inner(기본, 교집합), left, right, outer(합집합)
  - on : 공통 키 / left_on, right_on : 열 이름 다를 때
  - left_index=True / right_index=True : 색인을 키로 사용
  - suffixes : 겹치는 열 이름 처리

- pd.concat(): 축 방향 이어 붙이기
  - axis="columns" : 열 방향 / 기본은 행 방향
  - keys : 계층적 색인 생성으로 출처 구분
  - join="inner" : 교집합만 / 기본은 outer
  - ignore_index=True : 색인 무시하고 새로 할당

- combine_first(): a의 NaN을 b 값으로 채움

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="956" height="437" alt="image" src="https://github.com/user-attachments/assets/c5fd2043-3459-40c0-a734-b241e2b5430f" />
<img width="962" height="443" alt="image" src="https://github.com/user-attachments/assets/210b94f6-0851-4cdb-8838-b3243d914261" />
<img width="962" height="483" alt="image" src="https://github.com/user-attachments/assets/8ef40271-c5db-40a9-a871-37b867d31ad5" />
<img width="963" height="369" alt="image" src="https://github.com/user-attachments/assets/3dc80bbe-e699-437a-a8c7-52190936b0cf" />
<img width="961" height="430" alt="image" src="https://github.com/user-attachments/assets/0be31674-4fbf-408c-b0c0-cb013d9b97c5" />


## 6. 재구성과 피벗 

### 개념정리

- stack() : 열 → 행 (넓은→긴), 기본적으로 NA 자동 제거
- unstack() : 행 → 열 (긴→넓은), level= 로 단계 지정
- pivot() : 긴 형식 → 넓은 형식

- set_index + unstack과 동일한 동작
- pd.melt() : 넓은 형식 → 긴 형식 (pivot의 역)
- id_vars : 유지할 열 / value_vars : 녹일 열

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="959" height="460" alt="image" src="https://github.com/user-attachments/assets/0fdc7b7b-6b3a-42cf-abd2-422148e2887f" />
<img width="959" height="386" alt="image" src="https://github.com/user-attachments/assets/c532b2b6-96b7-4a75-bc56-cdeb54345ca5" />




# 2️⃣ 실습 과제

각 문제에 대한 실행 결과가 확인되도록 코드를 작성하고 실행한 뒤, **모든 문제의 실행 화면을 캡처하여 제출하시기 바랍니다.**

**1. 아래 코드를 실행하여 분석에 필요한 기초 데이터를 생성합니다.**
```python
import pandas as pd
import numpy as np

# 1. 고객 기본 정보
customers = pd.DataFrame({
    "customer_id": [101, 102, 103, 101, 104, 105],
    "name": ["Kim", "Lee", "Park", "Kim", "Choi", "Jung"],
    "age": [23, 35, 45, 23, 18, 55],
    "email": ["kim@gmail.com", "lee@naver.com", "park@gmail.com", "kim@gmail.com", "choi@naver.com", "jung@gmail.com"]
})

# 2. 구매 이력 정보
purchases = pd.DataFrame({
    "customer_id": [101, 102, 103, 106],
    "product": ["iPhone", "iPad", "MacBook", "Watch"],
    "amount": [1500, 800, 2500, 500]
})
```

**2. 문제**
```
1. 중복 고객 제거 및 연령대 그룹화
  - 문제 설명: 고객의 연령대 나누기 
  - drop_duplicates()를 사용하여 customer_id 기준 중복을 제거하세요.
  - pd.cut()을 사용하여 나이(age)를 10대(10-19), 20대(20-29), 30대 이상(30-100)으로 나누고 age_group 열을 만드세요.
  - print()를 이용해 정제된 고객 데이터프레임을 출력하세요.

2. 이메일 도메인 추출
  - 문제 설명: 고객들의 이메일 도메인(gmail, naver 등) 정보만 추출 
  - str.split()과 str.get()을 사용하여 이메일 주소에서 @ 뒷부분의 도메인만 추출하여 domain 열을 만드세요.
  - print()를 이용해 도메인이 추가된 결과를 출력하세요.

3. 고객 정보와 구매 이력 병합
  - 문제 설명: 고객 정보와 구매 이력을 하나로 합치기 
  - pd.merge()를 사용하여 customers와 purchases를 customer_id 기준으로 합치세요.
  - 이때 구매 이력이 없는 고객 정보도 모두 유지되도록 외부 조인(Outer Join) 방식을 사용하세요.
  - print()를 이용해 병합된 최종 데이터프레임을 출력하세요.
```


<img width="959" height="320" alt="image" src="https://github.com/user-attachments/assets/b41975ad-8334-4564-8b55-f387168dcd02" />
~~~
1번 문제
~~~

<img width="958" height="198" alt="image" src="https://github.com/user-attachments/assets/1c363519-1431-476d-bac5-8a93d6de171b" />
~~~
2번 문제
~~~

<img width="960" height="295" alt="image" src="https://github.com/user-attachments/assets/e9bbc8ba-9417-49c5-b15d-fdfe8ad82416" />
~~~
3번 문제
~~~





### 🎉 수고하셨습니다.







