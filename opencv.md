좋습니다! 아래는 컴퓨터 비전 라이브러리인 \*\*OpenCV (Open Source Computer Vision Library)\*\*에 대한 개념, 주요 기능, 자주 사용하는 함수들을 **한눈에 정리**한 내용입니다.
마크다운 형식도 포함해서 GitHub 문서로도 사용하실 수 있습니다.

---

## 📘 OpenCV 정리

````markdown
# 🖼️ OpenCV 정리 (Python 기반)

## 📌 OpenCV란?

- **OpenCV (Open Source Computer Vision Library)**는 컴퓨터 비전 및 이미지 처리에 사용되는 오픈소스 라이브러리입니다.
- 주로 **영상 분석, 얼굴 인식, 객체 검출, 실시간 카메라 처리 등** 다양한 분야에서 사용됩니다.
- C++, Python, Java 등 다양한 언어 지원.

---

## 📦 설치

```bash
pip install opencv-python
````

필요 시 GUI 기능 포함하려면:

```bash
pip install opencv-python-headless
```

---

## 📂 주요 기능

| 기능       | 설명                       |
| -------- | ------------------------ |
| 이미지 처리   | 필터, 경계선 검출, 변환 등         |
| 비디오 처리   | 실시간 스트리밍, 프레임 캡처         |
| 객체 검출    | 얼굴, 눈, 사람, 차 등 검출        |
| 머신러닝     | SVM, KNN, 딥러닝 모델 추론 지원   |
| 기하학 변환   | 회전, 크기 조절, 변형 등          |
| 컬러 공간 변환 | BGR ↔ RGB, 그레이스케일, HSV 등 |

---

## 🧪 자주 쓰는 코드 예제

### 1. 이미지 불러오기, 보여주기, 저장하기

```python
import cv2

# 이미지 불러오기
img = cv2.imread('image.jpg')

# 이미지 보기
cv2.imshow('My Image', img)
cv2.waitKey(0)  # 키 입력 기다림
cv2.destroyAllWindows()

# 이미지 저장
cv2.imwrite('saved_image.jpg', img)
```

---

### 2. 이미지 크기 조절

```python
resized = cv2.resize(img, (300, 300))
```

---

### 3. 색상 변환 (BGR → Gray)

```python
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
```

---

### 4. 블러 처리 (가우시안 블러)

```python
blurred = cv2.GaussianBlur(img, (5, 5), 0)
```

---

### 5. Canny 엣지 검출

```python
edges = cv2.Canny(img, 100, 200)
```

---

### 6. 도형 그리기

```python
# 선
cv2.line(img, (0,0), (100,100), (255,0,0), 2)

# 원
cv2.circle(img, (150,150), 50, (0,255,0), 3)

# 사각형
cv2.rectangle(img, (50,50), (200,200), (0,0,255), 2)
```

---

### 7. 글자 넣기

```python
cv2.putText(img, 'Hello OpenCV', (10,50), cv2.FONT_HERSHEY_SIMPLEX, 1, (255,255,255), 2)
```

---

## 📸 실시간 카메라 사용

```python
cap = cv2.VideoCapture(0)  # 0: 기본 웹캠

while True:
    ret, frame = cap.read()
    if not ret:
        break

    cv2.imshow('Camera', frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):  # q 누르면 종료
        break

cap.release()
cv2.destroyAllWindows()
```

---

## 🎯 주요 활용 분야

* 얼굴 인식(Face Recognition)
* 차량 번호판 인식(ANPR)
* 손 제스처 인식
* OCR (광학 문자 인식, Tesseract와 함께)
* 객체 추적
* 증강 현실(AR)

---

## 📚 참고 사이트

* 공식 문서: [https://docs.opencv.org](https://docs.opencv.org)
* GitHub: [https://github.com/opencv/opencv](https://github.com/opencv/opencv)

```

---

필요하시면 `이미지 필터 적용`, `YOLO로 객체 검출`, `OpenCV + 딥러닝 모델` 등 더 심화 예제도 드릴 수 있어요.  
특정 프로젝트에 적용하실 건가요? 목적에 맞춰 정리해드릴 수도 있어요.
```
