# 머신러닝 학습 유형
머신러닝은 크게 다음 세 가지 방식으로 분류됩니다:
- **지도학습 (Supervised Learning)**
- **비지도학습 (Unsupervised Learning)**
- **강화학습 (Reinforcement Learning)**
---
## 📘 지도학습 (Supervised Learning)
**정의**: 입력 데이터와 이에 대응하는 **정답(Label)**을 이용해 모델을 학습시키는 방식입니다.
**목표**: 새로운 입력에 대한 정답을 예측하는 모델을 만드는 것.
### ✅ 예시
- 이메일 스팸 분류
- 이미지 속 객체 분류
- 집값 예측
### 📌 대표 알고리즘
- Linear Regression (선형 회귀)
- Logistic Regression (로지스틱 회귀)
- Decision Tree (의사결정나무)
- Random Forest (랜덤 포레스트)
- SVM (Support Vector Machine)
- Neural Networks (신경망)
---
## 📙 비지도학습 (Unsupervised Learning)
**정의**: 정답 없이 데이터의 구조나 패턴을 학습하는 방식입니다.
**목표**: 데이터 내의 군집, 차원 축소, 이상치 등을 찾아내는 것.
### ✅ 예시
- 고객 군집화
- 데이터 시각화를 위한 차원 축소
- 이상치 탐지
### 📌 대표 알고리즘
- K-Means Clustering
- DBSCAN
- Hierarchical Clustering
- PCA (Principal Component Analysis)
- t-SNE, UMAP
---
## 📕 강화학습 (Reinforcement Learning)
**정의**: 에이전트가 환경과 상호작용하며 **보상(Reward)**을 최대화하는 방향으로 학습하는 방식입니다.
**목표**: 장기적인 보상을 극대화하는 행동 정책(Policy)을 학습하는 것.
### ✅ 예시
- 알파고, 체스 등 게임 AI
- 자율 주행 자동차
- 로봇 제어
### 📌 주요 구성요소
- 상태 (State)
- 행동 (Action)
- 보상 (Reward)
- 정책 (Policy)
- 가치 함수 (Value Function)
### 📌 대표 알고리즘
- Q-Learning
- SARSA
- DQN (Deep Q-Network)
- PPO (Proximal Policy Optimization)
- A3C, DDPG
---
> 💡 각각의 학습 방식은 문제의 특성과 목표에 따라 선택되며, 실제 프로젝트에서는 이들을 혼합하거나 조합해서 사용하기도 합니다.
필요하면 각 항목에 예제 코드 블록이나 다이어그램도 추가해드릴 수 있습니다. GitHub용 문서화가 더 필요하시면 말씀해주세요!


