# Python 5주차 정규 과제 

📌Python 정규과제는 매주 정해진 분량의 『*파이썬 라이브러리를 활용한 데이터 분석*』 을 읽고 학습하는 것입니다. 이번주는 아래의 **Python_5th_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 참고 자료를 통해 보완하는 것이 좋습니다.

**교재 실습 예제 파일은 07_Python_Template 레포지토리의 notebooks 폴더에 업로드되어 있습니다.**

**아나콘다 환경에서는 많은 패키지가 기본적으로 포함되어 있어 별도의 설치 없이 사용할 수 있지만, 환경에 따라 conda install이나 pip install이 필요할 수 있습니다.**

**👀(수행 인증샷은 필수입니다.)** 

## Python_5th_TIL

### 6장 데이터 로딩과 저장, 파일 형식
#### 1. 텍스트 파일에서 데이터를 읽고 쓰는 법
#### 2. 이진 데이터 형식
#### 3. 웹 API와 함께 사용하기
#### 4. 데이터베이스와 함께 사용하기
#### 5. 마치며
### 7장 데이터 정제 및 준비
#### 1. 누락된 데이터 처리하기
#### 2. 데이터 변형 


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.25~82    | ✅         |
| 2주차 | p.83~129   | ✅         |
| 3주차 | p.131~179  | ✅         |
| 4주차 | p.181~246 | ✅         |
| 5주차 | p.247~309 | ✅         |
| 6주차 | p.310~379 | 🍽️         |
| 7주차 | p.381~465 | 🍽️         |


<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 학습 내용 정리

## 1. 텍스트 파일에서 데이터를 읽고 쓰는 법

### 개념정리

- 색인: 반환하는 DataFrame에서 하나 이상의 열을 색인으로 지정할 수 있다. 파일이나 사용자로부터 열 이름을 받거나 아무것도 받지 않을 수 있다.
- 자료형 추론과 데이터 변환: 사용자 정의 값 변환과 비어 있는 값을 위한 사용자 리스트를 포함한다.
- 날짜 및 시간 분석: 여러 열에 걸쳐 있는 날짜와 시간 정보를 하나의 열에 조합해서 결과에 반영한다.
- 반복: 여러 개의 파일에 걸쳐 있는 자료를 반복적으로 읽어온다.
- 정제되지 않은 데이터 처리: 행이나 꼬리말, 주석 건너뛰기 또는 천 단위마다 쉼표로 구분된 숫자 같은 사소한 요소로 처리한다.

1. 텍스트 파일 조금씩 읽어오기
   - 파일 전체를 읽는 대신 처음 몇 행만 읽어보고 싶다면 nrows 옵션을 설정한다.
   - 파일을 여러 조각으로 나누어서 읽고 싶다면 chunksize 옵션으로 행 개수를 설정한다.

2. 데이터를 텍스트 형식으로 기록하기
   - 읽어오기와 마찬가지로 데이터를 구분자로 구분한 형식으로 내보내는 것도 가능하다.
   - to_csv 메서드를 이요하면 데이터를 쉼표로 구분된 형식으로 파일에 쓸 수 있다.
   - 누락된 값은 비어 있는 문자열로 나타나는데, 이것 역시 원하는 값으로 지정 가능하다.

3. 다른 구분자 형식 다루기
   - pandas.read_csv 같은 형식 말고 수동으로 처리해야 하는 경우도 있다.
   - 파일을 읽듯 reader를 순회하면 둘러싸고 있던 큰 따옴표가 제거된 리스트를 얻을 수 있다.
   - 딕셔너리 표기법과 행을 열로 전치해주는 zip(*values)를 이용해서 데이터 열 딕셔너리를 만들었다.

4. JSON 데이터
   - JSON은 웹 브라우저와 다른 애플리케이션이 HTTP 요청으로 데이터를 보낼 때 널리 사용하는 표준 파일 형식 중 하나다.
   - JSON은 CSV 같은 표 형식의 텍스트보다 좀 더 유연한 데이터 형식이다.
   - 객체의 키는 반드시 문자열 이어야 한다.
   - JSON 문자열을 파이썬 형태로 변환하기 위해서는 json.loads를 사용한다.
   - json.dumps는 파이썬 객체를 JSON 형태로 반환한다.

5. XML과 HTML: 웹 스크래핑
   - lxml은 가장 빠르게 작동하고 깨진 HTML과 XML파일도 잘 처리한다.
   - pandas.read_html 함수에는 다양한 옵션이 있는데 기본적으로<table> 태그 안에 모든 형식의 데이터 파싱을 시도한다 -> DataFrame 객체의 리스트에 저장됨.

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->


<img width="957" height="361" alt="image" src="https://github.com/user-attachments/assets/a82c9010-a3fe-41e6-9f78-5c6e87419e25" />

<img width="967" height="394" alt="image" src="https://github.com/user-attachments/assets/99b17216-b6d0-4714-9dab-daf3af7e6b71" />

<img width="956" height="469" alt="image" src="https://github.com/user-attachments/assets/b7e30227-21e8-4192-97b5-609efcc35d19" />

<img width="961" height="444" alt="image" src="https://github.com/user-attachments/assets/42d1a959-7881-4748-b6db-e27409c15bbe" />


## 2. 이진 데이터 형식

### 개념정리

- 데이터를 이진 형식으로 저장하는 가장 간단한 방법은 파이썬 내장 pickle 모듈을 이용하는 것이다.
- 판다스 객체는 pickle 형식으로 데이터를 디스크에 저장할 수 있는 to_pickle 메서드를 제공한다.

1. 마이크로소프트 엑셀 파일 읽기
   - pandas.ExcelFile 클래스나 pandas.read_excel 함수를 통해 표 형식의 엑셀 파일을 읽을 수 있다.
   - parse 함수를 통해 DataFrame으로 읽어올 수 있다.
   - index_col을 사용해 색인 열을 인수로 지정할 수 있다.
   - 간단하게 파일 이름을 pandas.read_excel에 넘겨줄 수 있다.
   - 판다스 데이터를 엑셀 형식으로 저장하려면 ExcelWriter 객체를 생성한 다음 판다스 객체의 to_excel 메서드를 이용해 데이터를 저장한다.

2. HDF5 형식 사용하기
   - 대량의 과학 계산용 배열 데이터를 저장하기 위해 고안된 훌륭한 파일 포맷이다.
   - 여러개의 데이터셋을 저장하고 부가 정보를 기록할 수 있다.

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="963" height="478" alt="image" src="https://github.com/user-attachments/assets/f421ce6d-0dea-489f-bc19-9297f2f9bb42" />

<img width="959" height="235" alt="image" src="https://github.com/user-attachments/assets/e93b19d6-d8be-427d-baab-1bbb8dc67c59" />


## 3. 웹 API와 함께 사용하기

### 개념정리

- 데이터 피드를 json이나 여타 다른 형식으로 얻을 수 있는 공개 API를 제공하는 웹사이트가 많다
- request 패키지다. 

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="966" height="395" alt="image" src="https://github.com/user-attachments/assets/8bd0e998-f490-46a0-a949-2afab0546f2e" />

<img width="958" height="484" alt="image" src="https://github.com/user-attachments/assets/63c764d5-9836-467a-83f0-81249a7c007a" />


## 4. 데이터베이스와 함께 사용하기

### 개념정리

- 판다스는 SQL 쿼리 결과를 간단하게 DataFrame으로 불러오는 함수를 몇 가지 제공한다.
- 파이썬 내장 sqlite3 드라이버를 이용해서 SQLite3 데이터베으스를 만들어보자.
- 대부분 파이썬 SQL 드라이버는 테이블에서 select 쿼리를 수행하면 튜플 리스트를 반환한다.
- 변환된 튜플 리스트를 DataFrame 생성자에 바로 전달해도 되지만, cursor의 description 속성에 있는 열 이름을 지정해야 한다.

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="961" height="337" alt="image" src="https://github.com/user-attachments/assets/1965f92d-f632-4ddf-ac91-e1b714e47d3f" />

<img width="961" height="478" alt="image" src="https://github.com/user-attachments/assets/efd127e0-d978-4f2f-8160-a3bc0742a183" />


## 5. 누락된 데이터 처리하기

### 개념정리

- isna 메서드는 값이 Null인 경우 True를 가지는 불리언 Series를 반환한다.
- 파이썬 내장 Nine 값 또한 NA 값으로 취급한다.

1. 누락된 데이터 골라내기
   - dropna를 사용하면 매우 쉽게 작업할 수 있다. 기본적으로 NA 값이 하나라도 있는 행을 제외한다.
   - how = 'all' 옵션을 넘기면 모든 값이 NA인 행만 제외된다.
   - 열을 제외하는 방법도 axis='columns'를 넘겨주면 된다.

2. 결측치 채우기
   - fillna를 사용해 누락된 값을 채워준다.
   - 딕셔너리 값을 넘기면 각 열마다 다른 값이 채워진다.
   - 평균값이나 중간값을 넘겨서 데이터를 채울 수 있다.

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->

<img width="961" height="482" alt="image" src="https://github.com/user-attachments/assets/8974ea35-c2f6-439a-adeb-85f48846cf3b" />

<img width="957" height="315" alt="image" src="https://github.com/user-attachments/assets/25b4bdeb-e3b5-48c1-b550-ff6ff7d465c8" />

<img width="960" height="324" alt="image" src="https://github.com/user-attachments/assets/fc3e1026-1180-413b-a82f-2a7beff470f3" />

## 6. 데이터 변형 

### 개념정리

1. 중복 제거하기
   - drop_duplicates는 duplicated 배열이 False인 DataFrame을 필터링해 반환한다.
   - keep = 'last' 옵션을 넘기면 마지막으로 발견된 값을 반환한다.

2. 함수나 매핑을 이용해서 데이터 변형하기
   - map 메서드는 변형을 위한 매핑 정보가 담긴 딕셔너리 같은 객체나 함수를 인수로 받는다.

3. 값 치환하기
   - replace 메서드는 치환작업을 더 간단하고 유연한 방식으로 제공한다.
   - 여러 개의 값을 한 번에 치환하려면 하나의 값 대신 치환하려는 값의 리스트를 넘기면 된다.

4. 축 색인 이름 바꾸기
   - 축 이름도 함수나 새롭게 바꿀 값을 이용해서 변형 할 수 있다.
   - map 메서드와 index에 바로 대입은 동일하다.

5. 이산화
   - pandas.cut 함수를 이용해서 나이에 대한 그룹을 나누어볼 수 있다.

6. 이상치를 찾고 제외하기
   - any메서드를 사용해 특정 조건을 만족하지 못하는 행들을 선택할 수 있다.

7. 뒤섞기와 임의 샘플링
   - numpy.random.permutation 함수를 이용하면 시리즈나 데이터프레임의 행을 임의의 순서대로 재배치 할 수 있다.

8. 표시자, 더미 변수 계산하기
   - 

### 실습 인증

<!-- 예제 실습을 진행한 후, 실행 화면을 2-3장 캡쳐하여 제출해주세요. -->


<img width="961" height="367" alt="image" src="https://github.com/user-attachments/assets/0d72f789-11c3-400e-ab0c-aa250ea5d5d9" />

<img width="962" height="158" alt="image" src="https://github.com/user-attachments/assets/d6a3d1aa-3167-4823-9ed1-34f23e9a9175" />

<img width="958" height="380" alt="image" src="https://github.com/user-attachments/assets/16cee2ca-ce08-4fb4-98ce-3f51f894e138" />

<img width="959" height="479" alt="image" src="https://github.com/user-attachments/assets/6a0171ee-72a9-4a13-a72f-a81dce760c61" />

<img width="964" height="479" alt="image" src="https://github.com/user-attachments/assets/1eab6693-59d6-4c82-8324-6a08c845773e" />


# 2️⃣ 실습 과제

각 문제에 대한 실행 결과가 확인되도록 코드를 작성하고 실행한 뒤, **모든 문제의 실행 화면을 캡처하여 제출하시기 바랍니다.**

**1. 아래 코드를 실행하여 텍스트와 데이터를 선언합니다.**
```python
import pandas as pd
import json
import requests

# 1. 테스트용 CSV 내용 (메모리 내 시뮬레이션용)
csv_data = "id,name,score,note\n1,Kim,85,NA\n2,Lee,NULL,Good\n3,Park,90,None"
with open("test_data.csv", "w") as f:
    f.write(csv_data)

# 2. 테스트용 JSON 문자열
json_obj = """
{
    "company": "DataService",
    "employees": [
        {"name": "Alice", "age": 30, "dept": "IT"},
        {"name": "Bob", "age": 25, "dept": "HR"}
    ]
}
"""
```

**2. 문제**
```
1. CSV 파일 읽기 및 결측치 지정
  - 문제 설명: 제공받은 test_data.csv 파일을 읽어오기(단, 데이터의 특성에 맞게 옵션 설정)
  - read_csv()를 사용하여 파일을 읽으세요.
  - 이때 NA, NULL, None이라는 문자열을 모두 **결측치(NaN)**로 인식하도록 na_values 옵션을 설정하세요.
  - print()를 이용해 읽어온 DataFrame을 출력하세요.

2. JSON 데이터 변환 및 특정 데이터 추출
  - 문제 설명: 문자열 형태의 JSON 데이터를 파싱하여 직원 명단만 추출
  - json.loads()를 사용하여 json_obj 문자열을 파이썬 객체로 변환하세요.
  - 변환된 객체에서 employees 리스트만 추출하여 DataFrame으로 만드세요.
  - print()를 이용해 생성된 직원 명단 DataFrame을 출력하세요.

3. 웹 API 데이터 가져오기
  - 문제 설명: 판다스 깃허브 저장소의 이슈(Issues) 데이터를 가져와 상위 항목 확인
  - requests.get()을 사용하여 https://api.github.com/repos/pandas-dev/pandas/issues URL의 데이터를 가져오세요.
  - 응답받은 JSON 데이터를 DataFrame으로 변환하세요.
  - print()를 이용해 데이터의 상단 5행(head)을 출력하세요.
```



<img width="1108" height="555" alt="image" src="https://github.com/user-attachments/assets/fc79b2da-2174-475a-afbb-8b01900e2d13" />

<img width="958" height="314" alt="image" src="https://github.com/user-attachments/assets/44aa0b69-4c03-4a6b-a8a2-8d333ab8b94d" />

<img width="957" height="291" alt="image" src="https://github.com/user-attachments/assets/c3fc36c9-8ed1-4031-84c7-43fbd506875d" />



### 🎉 수고하셨습니다.







