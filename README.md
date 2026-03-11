업로드된 PDF 파일이 만료되어 현재 내용을 확인할 수 없다. 다시 업로드하면 그 내용을 기반으로 정확한 README를 작성할 수 있다.

다만, 포트폴리오용으로 **채용 담당자가 선호하는 README 구조**는 다음과 같은 형태다. 이 구조는 데이터 분석 포트폴리오에서 가장 많이 사용되는 방식이다.

---

# Individual Baseline Deviation Detection in Wearable Health Data

웨어러블 센서 데이터를 기반으로 **개인별 정상 패턴(baseline)에서 벗어나는 이상 신호를 탐지하는 비지도 학습 프로젝트**입니다.
집단 평균이 아닌 **개인 기준 데이터 패턴을 학습하여 deviation을 탐지하는 접근**을 실험했습니다.

---

# Why This Project Matters

웨어러블 헬스 데이터 분석에서 자주 발생하는 문제:

같은 생체 지표라도 사람마다 정상 범위가 다릅니다.

예시

| Heart Rate | Person A | Person B |
| ---------- | -------- | -------- |
| 90 bpm     | 정상       | 이상       |

즉 **population average 기반 이상 탐지에는 한계**가 있습니다.

이 프로젝트는 다음 질문을 해결하려고 합니다.

> 개인의 평소 패턴에서 벗어나는 신호를 자동으로 탐지할 수 있을까?

---

# Project Goal

본 프로젝트의 목표

* wearable sensor 데이터 분석
* 개인 baseline 기반 이상 탐지
* 비지도 학습 기반 anomaly detection 구현
* end-to-end 데이터 분석 pipeline 구축

---

# Dataset

웨어러블 센서 기반 생체 데이터

### Observations

```
5,000 samples
14 features
```

### Sensor Features

생체 신호

* Heart Rate
* Blood Oxygen
* Body Temperature
* Respiratory Rate

활동 데이터

* Step Count
* Accelerometer (3-axis)
* Gyroscope (3-axis)

Context 정보

* Activity
* Timestamp

데이터 특징

* 결측치 없음
* 다중 센서 데이터
* 개인 활동 컨텍스트 포함

---

# Project Workflow

전체 분석 과정

```
EDA
 ↓
Correlation Analysis
 ↓
Feature Scaling
 ↓
Unsupervised Modeling
 ↓
Deviation Detection
```

---

# Exploratory Data Analysis

EDA에서 확인한 내용

### 1 Feature Distribution

* 주요 생체 데이터 분포 확인
* 센서 값 이상 여부 점검

### 2 Feature Correlation

두 가지 방법 사용

Pearson Correlation
Spearman Correlation

목적

* 변수 간 관계 확인
* 다중공선성 파악
* 모델 입력 안정성 확보

---

# Modeling Strategy

이 프로젝트는 **비지도 이상 탐지 문제**로 접근했습니다.

핵심 아이디어

```
정상 데이터 패턴 학습
↓
개인 baseline 형성
↓
baseline에서 벗어난 데이터 탐지
```

---

# Key Insights

프로젝트 진행 과정에서 얻은 주요 인사이트

### 1 Individual-Level Modeling

집단 평균이 아닌 **개인 baseline 기반 분석 필요성 확인**

---

### 2 Sensor Data Complexity

웨어러블 데이터 특징

* high dimensional sensor data
* noise 존재
* activity context 영향

---

### 3 Unsupervised Learning Applicability

라벨이 없는 상황에서도 **이상 패턴 탐지가 가능함을 확인**

---

# Repository Structure

```
wearable-anomaly-detection
│
├── data
│   └── wearable_dataset.csv
│
├── notebooks
│   ├── 01_EDA.ipynb
│   ├── 02_Preprocessing.ipynb
│   └── 03_Modeling.ipynb
│
├── src
│   ├── preprocessing.py
│   └── modeling.py
│
└── README.md
```

---

# Skills Demonstrated

이 프로젝트에서 사용한 데이터 분석 기술

* Python
* Pandas
* NumPy
* Data Visualization
* Correlation Analysis
* Feature Scaling
* Unsupervised Learning
* Anomaly Detection

---

# Future Improvements

추가적으로 확장 가능한 방향

* Time-series anomaly detection
* 개인 baseline dynamic modeling
* physiological stress detection
* activity-aware anomaly detection

---

# Author

Seonjae Yun

