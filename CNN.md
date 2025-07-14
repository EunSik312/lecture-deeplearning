\*\*CNN (Convolutional Neural Network)\*\*
| Term                                 | Description                                                                                         |
| ------------------------------------ | --------------------------------------------------------------------------------------------------- |
| **Convolution**                      | Sliding a filter (kernel) over the input to extract features like edges, textures, etc.             |
| **Kernel / Filter**                  | A small matrix used to perform convolution operation; detects patterns in the input.                |
| **Stride**                           | The step size by which the kernel moves across the input.                                           |
| **Padding**                          | Adding extra borders (usually zeros) around the input to preserve spatial dimensions.               |
| **ReLU (Rectified Linear Unit)**     | Activation function that replaces negative values with zero to introduce non-linearity.             |
| **Pooling**                          | Downsampling operation (e.g., max pooling, average pooling) to reduce spatial size.                 |
| **Max Pooling**                      | Retains the maximum value in each patch of the feature map.                                         |
| **Average Pooling**                  | Computes the average of values in each patch.                                                       |
| **Feature Map**                      | The output of a convolutional layer, representing learned features.                                 |
| **Flatten**                          | Converts multi-dimensional feature maps into a 1D vector before the fully connected layers.         |
| **Fully Connected Layer (FC Layer)** | Each neuron is connected to all neurons in the previous layer; used for classification.             |
| **Dropout**                          | Regularization technique that randomly disables neurons during training to prevent overfitting.     |
| **Epoch**                            | One complete pass through the entire training dataset.                                              |
| **Batch Size**                       | Number of training samples processed before the model's internal parameters are updated.            |
| **Backpropagation**                  | Algorithm for updating weights using gradients computed from loss.                                  |
| **Gradient Descent**                 | Optimization algorithm to minimize loss by updating weights in the direction of negative gradients. |
| **Overfitting**                      | When the model performs well on training data but poorly on unseen data.                            |
| **Underfitting**                     | When the model fails to capture patterns in the training data.                                      |
| **Regularization**                   | Techniques (e.g., L2, dropout) used to reduce overfitting.                                          |
| **Activation Map**                   | Another term for a feature map, emphasizing the effect of activation functions.                     |

## 경계 검출 필터 (Edge Detection)

**수직 경계 검출 필터**
```
[-1  0  1]
[-2  0  2]
[-1  0  1]
```
- Sobel 수직 필터
- 세로 선, 수직 경계 강조
- 좌우 밝기 차이 감지

**수평 경계 검출 필터**
```
[-1 -2 -1]
[ 0  0  0]
[ 1  2  1]
```
- Sobel 수평 필터
- 가로 선, 수평 경계 강조
- 상하 밝기 차이 감지

**Prewitt 필터**
```
수직: [-1  0  1]    수평: [-1 -1 -1]
     [-1  0  1]          [ 0  0  0]
     [-1  0  1]          [ 1  1  1]
```
- Sobel과 유사하지만 가중치 다름
- 노이즈에 더 민감

**Laplacian 필터**
```
[ 0 -1  0]
[-1  4 -1]
[ 0 -1  0]
```
- 모든 방향 경계 검출
- 2차 미분 연산자
- 노이즈에 민감

## 블러 필터 (Blur/Smoothing)

**평균 필터 (Average Filter)**
```
[1/9  1/9  1/9]
[1/9  1/9  1/9]
[1/9  1/9  1/9]
```
- 주변 픽셀들의 평균값
- 단순한 노이즈 제거
- 경계도 함께 흐려짐

**가우시안 필터 (Gaussian Filter)**
```
[1/16  2/16  1/16]
[2/16  4/16  2/16]
[1/16  2/16  1/16]
```
- 정규분포 기반 가중치
- 자연스러운 블러 효과
- 노이즈 제거에 효과적

**모션 블러 필터**
```
대각선: [1/3  0   0 ]
       [0   1/3  0 ]
       [0   0   1/3]
```
- 움직임 효과 시뮬레이션
- 방향성 있는 블러

## 샤프닝 필터 (Sharpening)

**기본 샤프닝 필터**
```
[ 0 -1  0]
[-1  5 -1]
[ 0 -1  0]
```
- 경계 강조로 선명도 향상
- 중앙값 증폭, 주변값 감소

**언샤프 마스킹 (Unsharp Masking)**
```
[-1/9 -1/9 -1/9]
[-1/9 17/9 -1/9]
[-1/9 -1/9 -1/9]
```
- 원본 - 블러 + 원본
- 세밀한 디테일 강조
- 사진 편집에서 널리 사용

## 특수 효과 필터

**엠보싱 필터 (Embossing)**
```
[-2 -1  0]
[-1  1  1]
[ 0  1  2]
```
- 3D 입체 효과
- 그림자와 하이라이트 생성
- 예술적 효과

**외곽선 강조 필터**
```
[-1 -1 -1]
[-1  8 -1]
[-1 -1 -1]
```
- 경계만 남기고 내부 제거
- 스케치 효과
- 윤곽선 추출

## 노이즈 제거 필터

**미디언 필터 (Median Filter)**
- 주변 픽셀들의 중간값 선택
- 소금-후추 노이즈 제거에 효과적
- 경계 보존하면서 노이즈 제거

**양방향 필터 (Bilateral Filter)**
- 거리와 픽셀값 차이 모두 고려
- 경계 보존하면서 스무딩
- 고급 노이즈 제거

## CNN에서의 활용

**초기 CNN 연구**
- 수작업으로 설계된 필터들 사용
- Gabor 필터, Sobel 필터 등을 초기 층에 적용
- 특정 패턴 감지를 위한 고정 필터

**현대 CNN**
- 학습 가능한 필터로 대체
- 데이터에서 자동으로 최적 필터 학습
- 하지만 여전히 전통적 필터의 개념을 기반으로 함

**하이브리드 접근**
- 전통적 필터를 초기값으로 사용
- fine-tuning을 통해 최적화
- 해석 가능한 특징 추출
