# Python 1주차 정규 과제 

📌Python 정규과제는 매주 정해진 분량의 『*파이썬 라이브러리를 활용한 데이터 분석*』 을 읽고 학습하는 것입니다. 이번주는 아래의 **Python_1st_TIL**에 나열된 분량을 읽고 공부하시면 됩니다.

아래의 문제를 풀어보며 학습 내용을 점검하세요. 문제를 해결하는 과정에서 개념을 스스로 정리하고, 필요한 경우 참고 자료를 통해 보완하는 것이 좋습니다.

**교재 실습 예제 파일은 07_Python_Template 레포지토리의 notebooks 폴더에 업로드되어 있습니다.**

**👀(수행 인증샷은 필수입니다.)** 

## Python_1st_TIL

### 1장 시작하기 전에
#### 1. 다루는 내용
#### 2. 데이터 분석에 파이썬을 사용하는 이유
#### 3. 필수 파이썬 라이브러리
#### 4. 설치 및 설정
#### 5. 커뮤니티와 콘퍼런스
#### 6. 이 책을 살펴보는 방법
### 2장 파이썬 기초, IPython과 주피터 노트북 
#### 1. 파이썬 인터프리터 
#### 2. IPython 기초 
#### 3. 파이썬 기초
#### 4. 마치며


## Study Schedule

| 주차  | 공부 범위     | 완료 여부 |
| ----- | ------------- | --------- |
| 1주차 | p.25~82    | ✅         |
| 2주차 | p.83~129   | 🍽️         |
| 3주차 | p.131~179  | 🍽️         |
| 4주차 | p.181~246 | 🍽️         |
| 5주차 | p.247~309 | 🍽️         |
| 6주차 | p.310~379 | 🍽️         |
| 7주차 | p.381~465 | 🍽️         |


<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 학습 내용 정리

## 1. 설치 및 설정 

```
아나콘다(Anaconda) 또는 미니콘다(Miniconda)를 설치한 후, 필수 패키지를 설치하고 설치 완료 화면을 캡처하여 제출해주세요.

```
<img width="1020" height="563" alt="image" src="https://github.com/user-attachments/assets/dcf3be38-c0be-4ffa-8ac3-ca6b5ba9640a" />


<!--  Python 실행 및 가상환경 관리가 가능한 환경(예: venv 등)이 이미 구축되어 있다면 해당 환경을 사용하셔도 괜찮습니다. 
이 경우 해당 환경의 시작 화면을 캡쳐해주세요.-->


## 2. 파이썬 인터프리터 

```
간단한 hello_world.py 파일을 생성한 후, Anaconda Prompt(또는 Miniconda Prompt)를 실행하세요.
(해당 파일에는 print('Hello World!')라고 입력해주세요.)
프롬프트에서 ipython을 입력하여 IPython 환경을 실행한 뒤, %run hello_world.py 명령어로 파일을 실행하시기 바랍니다.
실행 결과가 나타난 화면을 캡처하여 제출해주세요.
```

<img width="877" height="176" alt="image" src="https://github.com/user-attachments/assets/3636527a-eadc-4c13-bd09-a8783d95e9a0" />



## 3. IPython 기초  

### IPython 셀 실행하기 
```
IPython을 실행한 후, 아래 코드를 한 줄씩 입력하여 실행해보세요. 각 명령어 실행 결과를 확인하고, 실행 화면을 캡처하여 제출해주세요.
```
```python
a = 5
a

import numpy as np
data = [np.random.standard_normal() for i in range(7)]
data
```

<img width="846" height="428" alt="image" src="https://github.com/user-attachments/assets/2bcb724c-aea1-43b7-9e5b-96ccfa3847fe" />


### 주피터 노트북 실행하기 

```
주피터 노트북을 실행한 후, 새로운 노트북을 생성하세요.
코드 셀에 print("Hello, World!")를 입력하고 실행한 뒤, 출력 결과가 나타난 화면을 캡처하여 제출해주세요.
```

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ef9dee8b-fc62-420e-b231-3c9e51d1c322" />



## 파이썬 기초  

<!-- 이 부분을 지우고 파이썬 기초에 대해 새롭게 배우게 된 내용을 정리해주세요. -->


---

# 2️⃣ 실습 과제

**주피터 노트북에서 아래의 코드 셀을 실행하고, 출력 결과를 캡처하여 제출하세요.**

```python
key = 7
data = [44059, 44050, 39, 52626, 54623, 38]

print("".join(chr(x ^ key) for x in data))
```

<img width="1912" height="935" alt="image" src="https://github.com/user-attachments/assets/9bd5d317-90e5-4914-a4f3-71765fcc4bde" />


### 🎉 수고하셨습니다.







