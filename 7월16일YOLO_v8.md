#YOLO_v8
- **기본 개념과 특징**: YOLOv8의 정의와 주요 장점
- **모델 아키텍처**: Backbone, Neck, Head 구조 설명
- **성능 벤치마크**: 다양한 모델 크기별 성능 비교
- **실제 사용 코드**: 설치부터 고급 사용법까지
- **활용 분야**: 실제 산업에서의 적용 사례
- **최적화 팁**: 성능 향상을 위한 실용적인 조언

!pip install ultralytics 

from google.colab import files

from ultralytics import YOLO # COCO 사전 훈련된 YOLOv8n 모델 로드

model = YOLO("yolov8n.pt")# 모델 정보 표시 (선택사항)

model.info() # COCO8 예제 데이터셋으로 100 에포크 훈련

results = model.train(data="coco8.yaml", epochs=10, imgsz=640) # 사진 업로드하고 경로 설정

uploaded = files.upload()

image_path = list(uploaded.keys())[0] # 업로드한 이미지에 대해 YOLOv8n 모델로 추론 실행

results = model(image_path)

results[0].show()

# YOLOv8 객체 탐지 코드 설명

이 코드는 Google Colab 환경에서 YOLOv8 모델을 사용하여 객체 탐지를 수행하는 전체 과정을 보여줍니다.

## 1. 라이브러리 설치 및 임포트

```python
!pip install ultralytics
from google.colab import files
from ultralytics import YOLO
```

- `ultralytics` 패키지를 설치합니다. 이는 YOLOv8의 공식 Python 패키지입니다.
- `google.colab.files`는 Colab에서 파일 업로드/다운로드를 위한 모듈입니다.
- `ultralytics.YOLO`는 YOLOv8 모델을 불러오고 사용하기 위한 클래스입니다.

## 2. 사전 훈련된 모델 로드

```python
model = YOLO("yolov8n.pt")
```

- COCO 데이터셋으로 사전 훈련된 YOLOv8n(nano) 모델을 로드합니다.
- `yolov8n.pt`는 가장 작고 빠른 YOLOv8 모델 변형입니다.
- 파일이 로컬에 없으면 자동으로 다운로드됩니다.

## 3. 모델 정보 확인

```python
model.info()
```

- 모델의 구조, 파라미터 수, 레이어 정보 등을 출력합니다.
- 선택사항이지만 모델 이해에 도움이 됩니다.

## 4. 모델 훈련

```python
results = model.train(data="coco8.yaml", epochs=10, imgsz=640)
```

- **data="coco8.yaml"**: COCO8 예제 데이터셋을 사용합니다 (COCO 데이터셋의 작은 샘플)
- **epochs=10**: 10번의 에포크 동안 훈련합니다
- **imgsz=640**: 입력 이미지 크기를 640x640으로 설정합니다

이 단계는 모델을 fine-tuning하는 과정입니다. 실제 프로젝트에서는 자신의 데이터셋을 사용할 수 있습니다.

## 5. 이미지 업로드

```python
uploaded = files.upload()
image_path = list(uploaded.keys())[0]
```

- `files.upload()`를 통해 Colab에 이미지 파일을 업로드합니다.
- 업로드된 파일의 경로를 `image_path` 변수에 저장합니다.
- `uploaded.keys()`는 업로드된 파일명들을 반환하며, 첫 번째 파일을 선택합니다.

## 6. 객체 탐지 수행

```python
results = model(image_path)
results[0].show()
```

- 업로드된 이미지에 대해 객체 탐지를 수행합니다.
- `model(image_path)`는 추론을 실행하고 결과를 반환합니다.
- `results[0].show()`는 탐지된 객체들이 표시된 이미지를 화면에 출력합니다.

## 주요 특징

- **사전 훈련된 모델**: COCO 데이터셋으로 훈련된 모델을 사용하여 80개 클래스의 객체를 탐지할 수 있습니다.
- **Fine-tuning**: 추가 훈련을 통해 특정 도메인에 맞게 모델을 개선할 수 있습니다.
- **실시간 추론**: 업로드된 이미지에 대해 즉시 객체 탐지를 수행합니다.

## 사용 시나리오

이 코드는 다음과 같은 상황에서 유용합니다:

- 객체 탐지 모델의 성능을 빠르게 테스트하고 싶을 때
- 자신의 이미지에 대해 YOLOv8의 탐지 성능을 확인하고 싶을 때
- 커스텀 데이터셋으로 모델을 fine-tuning하고 결과를 확인하고 싶을 때

## 참고사항

- YOLOv8n은 속도는 빠르지만 정확도는 상대적으로 낮습니다. 더 높은 정확도가 필요하면 `yolov8s.pt`, `yolov8m.pt`, `yolov8l.pt`, `yolov8x.pt` 등을 사용할 수 있습니다.
- 훈련 시간은 에포크 수와 데이터셋 크기에 따라 달라집니다.
- GPU를 사용하면 훈련과 추론 속도를 크게 향상시킬 수 있습니다.

| 용어                                | 설명                                                                                                  |
| --------------------------------- | --------------------------------------------------------------------------------------------------- |
| **YOLO** (You Only Look Once)     | 이미지를 한 번만 보는 방식으로 객체를 빠르게 탐지하는 딥러닝 모델 시리즈입니다.                                                       |
| **Ultralytics**                   | YOLO 모델 (특히 YOLOv5\~v8)을 개발하고 배포한 회사 또는 GitHub 프로젝트입니다.                                             |
| **YOLOv8**                        | Ultralytics에서 만든 최신 YOLO 모델로, 객체 탐지 외에도 분류(Classification), 분할(Segmentation), 자세 추정(Pose) 등도 지원합니다. |
| **Bounding Box (bbox)**           | 객체를 감싸는 사각형 박스. `(x, y, w, h)` 형태로 좌표를 표현합니다.                                                       |
| **Confidence Score**              | 탐지된 객체가 맞을 확률. 예: 고양이로 인식한 확률이 0.92 (92%)                                                           |
| **Class (Label)**                 | 인식하려는 객체의 종류. 예: 고양이, 개, 사람 등                                                                       |
| **mAP (mean Average Precision)**  | 모델의 성능을 나타내는 지표. 값이 1에 가까울수록 정확한 탐지입니다.                                                             |
| **IoU (Intersection over Union)** | 예측한 박스와 실제 정답 박스가 얼마나 겹치는지를 수치로 표현한 값.                                                              |
| **NMS (Non-Maximum Suppression)** | 겹치는 박스 중에서 가장 확신(confidence)이 높은 것만 남기고 나머지는 제거하는 과정.                                               |
| **Anchor Box**                    | 다양한 크기의 객체를 탐지할 수 있도록 사전에 정의된 박스. YOLOv8은 앵커리스(anchor-free) 구조를 채택함.                                |
| **Epoch**                         | 전체 학습 데이터를 한 번 학습하는 것을 한 에폭이라고 합니다. 보통 여러 에폭을 반복합니다.                                                |
| **Batch Size**                    | 한 번에 학습에 사용하는 이미지 수입니다.                                                                             |
| **Learning Rate**                 | 모델이 얼마나 빠르게 학습하는지를 조절하는 값입니다. 너무 크면 불안정하고, 너무 작으면 느립니다.                                             |
| **Loss**                          | 예측값과 정답의 차이. 학습 중 이 값을 줄이는 것이 목적입니다.                                                                |
| **Data Loader**                   | 이미지와 라벨 데이터를 모델이 읽을 수 있게 불러오는 코드입니다.                                                                |
| **COCO Format**                   | 객체 탐지용 데이터 포맷 중 하나. YOLOv8은 이 형식도 지원합니다.                                                            |
| **ONNX, TensorRT**                | 학습한 모델을 다양한 환경에서 사용할 수 있도록 변환하는 포맷. 배포용으로 많이 사용됩니다.                                                 |
| **Train / Val / Test**            | 각각 학습용, 검증용, 테스트용 데이터셋을 의미합니다.                                                                      |
| **Segmentation**                  | 객체를 픽셀 단위로 인식하는 작업입니다. YOLOv8에서는 `--task segment` 옵션으로 가능.                                          |
| **Classification**                | 이미지가 무엇인지 분류하는 작업. 예: 개냐 고양이냐                                                                       |
| **Pose Estimation**               | 사람의 관절 위치를 인식하는 작업입니다.                                                                              |
| **Ultralytics HUB**               | Ultralytics에서 제공하는 웹 기반 인터페이스. 모델 학습, 관리, 배포 등을 쉽게 할 수 있습니다.                                        |

