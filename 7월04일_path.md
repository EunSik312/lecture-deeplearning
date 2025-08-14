## 📁 1. 이미지 경로 복사해서 할 수 있는 일

| 작업              | 설명                         | 예시                                             |
| --------------- | -------------------------- | ---------------------------------------------- |
| 이미지 불러오기        | `cv2.imread()`로 불러오기       | `cv2.imread('/content/image.jpg')`             |
| PIL로 열기         | 이미지 분석, 변환                 | `Image.open('/content/image.jpg')`             |
| Matplotlib에 띄우기 | 시각화용                       | `plt.imshow(cv2.imread('/content/image.jpg'))` |
| 모델 입력으로 사용      | CNN, YOLO 등 모델 테스트에 활용     | 모델에 직접 이미지 넣기                                  |
| 파일 이동/복사        | `shutil`, `os.rename` 등 사용 | `/content/image.jpg` → `/content/sample/`      |

---

## 🧪 예제: 경로 복사해서 OpenCV로 이미지 불러오기

1. 코랩에 이미지 업로드
2. 이미지 우클릭 → 경로 복사 (`/content/파일명.jpg` 형태)

```python
import cv2
from matplotlib import pyplot as plt

# 경로 복사한 이미지 경로 사용
img_path = '/content/sample_image.jpg'
img = cv2.imread(img_path)

# OpenCV는 BGR이라 RGB로 변환 후 시각화
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb)
plt.title("Loaded Image")
plt.axis('off')
plt.show()
```

---

## 📌 주의할 점

* 이미지 경로는 항상 `/content/` 또는 `/content/drive/`로 시작해요.
* 드라이브에 접근하려면 `drive.mount()`를 먼저 해줘야 해요.

```python
from google.colab import drive
drive.mount('/content/drive')
```

---

필요하면 **Colab에서 이미지 업로드 방법**, **YOLO 입력으로 변환**, **파일 이동/삭제 코드**도 알려줄 수 있어요.
