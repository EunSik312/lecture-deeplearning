## 🧠 CNN 자주 사용되는 용어

### 1. **Input (입력)**

* CNN에 들어가는 원본 데이터 (보통 이미지)
* 예: 224x224x3 → 너비 224, 높이 224, 채널 3 (RGB 이미지)

---

### 2. **Kernel / Filter (커널 또는 필터)**

* 입력 이미지 위를 움직이며 특징을 추출하는 작은 행렬
* 보통 크기는 3x3, 5x5 등
* 커널은 **Convolution 연산**의 주체

---

### 3. **Convolution (합성곱)**

* 커널을 이미지에 적용해 특징을 추출하는 연산
* 예: 에지(edge), 코너(corner), 텍스처 등을 감지

---

### 4. **Stride (스트라이드)**

* 커널이 움직이는 간격
* Stride=1이면 한 칸씩, Stride=2면 두 칸씩 이동
  → 크기가 줄어들며 연산 속도 증가

---

### 5. **Padding (패딩)**

* 경계 부분 정보 손실을 막기 위해, 입력 이미지 가장자리에 0 등을 추가
* 종류:

  * **Valid**: 패딩 없이 → 크기 줄어듦
  * **Same**: 출력 크기를 입력과 같게 유지하려고 패딩 추가

---

### 6. **Feature Map (특징 맵)**

* Convolution 결과로 얻어진 출력
* 각 필터가 감지한 이미지의 특징을 담고 있음

---

### 7. **Activation Function (활성화 함수)**

* 비선형성을 추가해 학습 능력 향상
* CNN에서는 주로 **ReLU (Rectified Linear Unit)** 사용

  * ReLU(x) = max(0, x)

---

### 8. **Pooling (풀링)**

* Feature map의 크기를 줄이는 과정
* 종류:

  * **Max Pooling**: 구역 내 최대값 추출
  * **Average Pooling**: 평균값 추출
    → 계산량 감소 + 과적합 방지

---

### 9. **Flatten**

* 마지막 Feature Map을 1차원 벡터로 변환
* 완전 연결층(FC Layer)에 입력하기 위해 사용

---

### 10. **Fully Connected Layer (FC Layer)**

* CNN의 마지막 단계
* Flatten된 데이터를 입력받아 \*\*최종 출력(예측)\*\*을 생성

---

### 11. **Epoch / Batch Size / Iteration**

* **Epoch**: 전체 데이터셋을 한 번 학습한 횟수
* **Batch Size**: 한 번에 학습하는 데이터 수
* **Iteration**: 한 Epoch 안에서 배치만큼 학습하는 횟수

---

### 12. **Overfitting (과적합) / Underfitting (과소적합)**

* 모델이 너무 복잡해서 훈련 데이터에만 잘 맞는 상태: **Overfitting**
* 모델이 너무 단순해서 학습이 잘 안 되는 상태: **Underfitting**

---

### 13. **Dropout**

* 학습 중 일부 뉴런을 랜덤하게 꺼서 과적합을 방지하는 기법

---

