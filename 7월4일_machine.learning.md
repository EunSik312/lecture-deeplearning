# 🧠 머신러닝 개요 (Overview of Machine Learning)
## 📌 머신러닝이란?
**머신러닝(Machine Learning)**은 명시적인 프로그래밍 없이 데이터로부터 학습하고 예측하거나 판단을 내리는 인공지능(AI)의 한 분야입니다.
전통적인 프로그래밍은 `입력 + 규칙 → 출력`의 구조이지만,  
머신러닝은 `입력 + 출력(데이터) → 규칙(모델)`을 학습합니다.
---
## 🧭 머신러닝의 주요 목적
- **패턴 인식**: 데이터에서 규칙과 패턴을 자동으로 추출
- **예측**: 과거 데이터를 바탕으로 미래 값을 예측
- **분류 및 군집화**: 데이터를 의미 있는 그룹으로 나누거나 라벨을 예측
---
## ⚙️ 머신러닝의 작동 원리
1. **데이터 수집 (Data Collection)**
2. **데이터 전처리 (Data Preprocessing)**
3. **특성 선택 및 추출 (Feature Engineering)**
4. **모델 선택 (Model Selection)**
5. **학습 (Training)**
6. **평가 (Evaluation)**
7. **예측/추론 (Prediction/Inference)**
---
## 🧩 머신러닝의 분류
머신러닝은 학습 방식에 따라 세 가지로 나눌 수 있습니다:
| 학습 방식     | 설명                                                                 |
|--------------|----------------------------------------------------------------------|
| 지도학습      | 입력과 정답(label)을 기반으로 모델을 학습                             |
| 비지도학습    | 정답 없이 데이터의 구조나 패턴을 찾음                                 |
| 강화학습      | 보상을 최대화하는 행동을 학습 (환경과 상호작용)                        |
> 📚 각 학습 유형은 [머신러닝 학습 유형](#머신러닝-학습-유형) 문서를 참고하세요.
---
## 🧠 머신러닝 vs 전통 프로그래밍 vs 딥러닝
| 항목         | 전통 프로그래밍           | 머신러닝                       | 딥러닝                          |
|--------------|----------------------------|--------------------------------|----------------------------------|
| 데이터 필요성 | 낮음                        | 높음                           | 매우 높음                        |
| 처리 대상     | 규칙 기반                  | 통계적 패턴                     | 대규모 비정형 데이터 (이미지 등) |
| 예시          | 계산기, 엑셀               | 스팸 필터, 가격 예측            | 이미지 분류, 음성 인식           |
---
## 📦 머신러닝 주요 라이브러리
- **Python**:
  - `scikit-learn`: 범용 머신러닝 라이브러리
  - `XGBoost`, `LightGBM`: 고성능 결정 트리 기반 알고리즘
- **딥러닝 프레임워크**:
  - `TensorFlow`, `Keras`, `PyTorch`
---
## 📚 참고 용어
- **정확도 (Accuracy)**, **정밀도 (Precision)**, **재현율 (Recall)**, **F1-score**
- **과적합 (Overfitting)** vs **과소적합 (Underfitting)**
- **교차 검증 (Cross-Validation)**
---
✅ 머신러닝은 자동화된 의사결정을 가능하게 하며, 금융, 의료, 제조, 게임, 자율주행 등 다양한 분야에 활용되고 있습니다.

# 📘 머신러닝 학습 방법 정리 (초보자용)
머신러닝은 컴퓨터가 **명시적인 규칙 없이 데이터로부터 스스로 학습**하는 기술입니다.  
학습 방식에 따라 크게 세 가지로 나눌 수 있습니다:
- 지도학습 (Supervised Learning)
- 비지도학습 (Unsupervised Learning)
- 강화학습 (Reinforcement Learning)
---
## ✅ 1. 지도학습 (Supervised Learning)
### 🧠 개념
정답(라벨)이 있는 데이터를 사용해서 학습하는 방식입니다.  
모델은 주어진 입력에 대해 정답을 예측하는 방법을 배웁니다.
예: 학생에게 문제와 정답을 모두 보여주고, 스스로 푸는 법을 익히게 하는 것
### 🔍 대표 예시
| 예시 | 설명 |
|------|------|
| 이메일 스팸 필터링 | 메일 내용 → 스팸 or 일반 메일 분류 |
| 손글씨 숫자 인식 | 이미지 → 숫자(0~9) 분류 |
| 집값 예측 | 집의 면적, 위치 → 가격 예측 |
### 🛠 사용 알고리즘
- 선형 회귀 (Linear Regression)
- 로지스틱 회귀 (Logistic Regression)
- 결정 트리 (Decision Tree)
- 랜덤 포레스트 (Random Forest)
- 신경망 (Neural Network)
---
## ✅ 2. 비지도학습 (Unsupervised Learning)
### 🧠 개념
정답이 없는 데이터를 사용해서 **패턴이나 그룹을 스스로 찾는** 학습 방식입니다.
예: 학생에게 정답 없이 문제만 주고, 스스로 문제 유형이나 패턴을 파악하게 하는 것
### 🔍 대표 예시
| 예시 | 설명 |
|------|------|
| 고객 군집화 | 고객 행동 데이터를 기반으로 비슷한 고객 그룹 만들기 |
| 이상치 탐지 | 거래 내역 중 비정상적인 패턴 찾기 |
| 차원 축소 | 고차원 데이터(예: 이미지)를 2D로 시각화 |
### 🛠 사용 알고리즘
- K-평균 클러스터링 (K-Means)
- DBSCAN
- 주성분 분석 (PCA)
- t-SNE, UMAP
---
## ✅ 3. 강화학습 (Reinforcement Learning)
### 🧠 개념
에이전트가 환경과 상호작용하면서 **보상(reward)을 최대화**하는 방향으로 학습하는 방식입니다.
예: 게임을 하면서 점수를 더 많이 얻는 방법을 스스로 배우는 것
### 🔍 대표 예시
| 예시 | 설명 |
|------|------|
| 알파고 | 바둑 게임에서 스스로 전략을 학습 |
| 자율 주행 | 도로 환경에서 사고 없이 주행하는 법을 학습 |
| 로봇 제어 | 로봇이 넘어지지 않고 걷는 방법을 스스로 학습 |
### 🛠 주요 개념
- 상태 (State)
- 행동 (Action)
- 보상 (Reward)
- 정책 (Policy)
### 🛠 사용 알고리즘
- Q-Learning
- DQN (Deep Q Network)
- PPO (Proximal Policy Optimization)
---
## 📌 요약
| 학습 방식 | 데이터 형태 | 목적 | 예시 |
|-----------|-------------|------|------|
| 지도학습 | 입력 + 정답 | 예측, 분류 | 스팸 분류, 가격 예측 |
| 비지도학습 | 입력만 있음 | 패턴/군집 발견 | 고객 분류, 이상치 탐지 |
| 강화학습 | 보상 기반 상호작용 | 최적의 행동 학습 | 게임, 자율 주행 |
---
> 💡 초보자일수록 먼저 **지도학습**부터 시작하고, 차차 **비지도학습**과 **강화학습**으로 넓혀가면 좋습니다!
이 문서는 GitHub에서 머신러닝 개요를 설명하거나 교육용 자료로 매우 유용합니다. 원하시면 코드 예제나 시각 자료도 추가해 드릴 수 있어요!


## 🐧 Seaborn이란?

#**Seaborn**은 Python에서 사용하는 **데이터 시각화 라이브러리**입니다.
#Matplotlib을 기반으로 하고 있으며, **통계적 그래프를 더 쉽게, 더 예쁘게** 만들 수 있도록 도와줍니다.

---

## ✅ 기본 사용법

```python
import seaborn as sns
import matplotlib.pyplot as plt
```

* `sns`는 `seaborn`의 **별칭(alias)** 으로 일반적으로 이렇게 불러옵니다.
* Matplotlib과 함께 사용하는 경우가 많습니다.

---

## 📊 예시: 간단한 그래프 그리기

### 1. **타이타닉 데이터셋 로드 & 시각화**

```python
import seaborn as sns
import matplotlib.pyplot as plt

# 내장 데이터셋 로드
titanic = sns.load_dataset("titanic")

# 성별에 따른 생존률 막대 그래프
sns.barplot(x="sex", y="survived", data=titanic)

plt.title("생존률 (성별)")
plt.show()
```

---

### 2. **히트맵 (Heatmap)**

```python
flights = sns.load_dataset("flights")
pivot = flights.pivot("month", "year", "passengers")

sns.heatmap(pivot, annot=True, fmt="d", cmap="YlGnBu")
plt.title("연도별 월별 비행기 탑승객 수")
plt.show()
```

---

## 🔧 자주 쓰는 함수

| 함수                  | 설명                      |
| ------------------- | ----------------------- |
| `sns.barplot()`     | 범주형 변수 막대 그래프           |
| `sns.countplot()`   | 항목별 개수 세기               |
| `sns.histplot()`    | 히스토그램                   |
| `sns.boxplot()`     | 상자 그림                   |
| `sns.heatmap()`     | 열 지도 (상관관계, 수치 데이터 시각화) |
| `sns.pairplot()`    | 여러 변수들의 관계 시각화          |
| `sns.scatterplot()` | 산점도 (점으로 데이터 표현)        |

---

## 📦 설치

Seaborn이 설치되어 있지 않다면, 아래 명령어로 설치할 수 있어요:

```bash
pip install seaborn
```

---

필요하시면 더 고급 예제나 한글폰트 설정, matplotlib 비교 등도 알려드릴게요!
`pandas`와 함께 쓰는 게 보통인데, 데이터프레임 연습도 도와드릴까요?

