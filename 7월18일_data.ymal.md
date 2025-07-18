
YOLO에서 **`yaml` 파일** 객체 감지 모델을 **훈련(train)** 할 때, **데이터셋의 정보**를 알려주는 **설정 파일**.
YOLO에서 데이터를 분석하는 것을 '추론'이라고한다.
---

## 📄 `yaml` 파일이란?

> **YAML (YAML Ain’t Markup Language)**: 사람이 읽기 쉬운 데이터 구조 파일 (Python의 딕셔너리처럼 생김)

---

## 📦 YOLO에서 `data.yaml`의 역할

YOLO는 훈련할 때 `data.yaml` 파일을 읽어서:

* 어떤 이미지로 훈련할지?
* 어떤 라벨(class)이 있는지?
* 클래스 이름은 뭔지?

이런 정보를 파악

---

## ✍️ 예시: `data.yaml` 내용

```yaml
# data.yaml

path: /content/dataset  # 전체 데이터셋 폴더 경로
train: images/train      # 학습 이미지 경로
val: images/val          # 검증 이미지 경로

names:
  0: person
  1: car
  2: traffic_light
```

---

## 📁 폴더 구조와 연결 예시

```bash
dataset/
├── images/
│   ├── train/
│   └── val/
├── labels/
│   ├── train/
│   └── val/
└── data.yaml  ← 이 파일이 전체 정보를 가지고 있음
```

> `images/`에는 `.jpg`, `.png` 파일
> `labels/`에는 YOLO 형식의 `.txt` 라벨 파일
> `data.yaml`은 이를 연결해 주는 안내서

---

## 🧪 YOLOv12에서 사용 예

```python
from ultralytics import YOLO

model = YOLO("yolov12n.yaml")  # 모델 구조 또는 가중치 지정
model.train(data="data.yaml", epochs=50, imgsz=640)
```

---

## ✅ 요약

| 항목        | 설명                               |
| --------- | -------------------------------- |
| **파일 이름** | `data.yaml`                      |
| **역할**    | YOLO 훈련 시 데이터셋 경로, 클래스 이름 정의     |
| **필수 항목** | `path`, `train`, `val`, `names`  |
| **형식**    | YAML 문법 (들여쓰기 주의, `.json`보다 간단함) |

---
