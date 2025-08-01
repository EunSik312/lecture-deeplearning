# 교육 시작

### 참고링크

https://org.ngc.nvidia.com/setup/installers/cli

https://github.com/NVIDIA-AI-IOT/deepstream_reference_apps

https://docs.google.com/document/d/1WUtXecVecKDd5b2omhBJMx-FiIq2zsVs_Fsetb5rdcE/edit?tab=t.0

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/0298aa80-e8c8-44b6-bf4e-adc7a4345a2a" />

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/e5d43cc4-5407-451f-bc15-1906f33e30ee" />

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/70bc356a-b9f5-45e0-a4bc-1ad4f9c9adf3" />

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/07975f06-89b7-4e00-a152-1c5d41a27f80" />


## qize

<img width="883" height="351" alt="image" src="https://github.com/user-attachments/assets/728a8a35-8e3f-45aa-a660-f16419116ee5" />

> classification : 이미지를 분류해서 어떤 객체가 있는지 결정

> object detection : 객체가 무엇이고 어디에 있는지 파악

> segmentation : 이미지에서 각 객체에 대해 픽셀 단위의 마스크를 생성하는 세분화

<img width="887" height="335" alt="image" src="https://github.com/user-attachments/assets/89bf9612-1d13-40c4-8c1f-f12924f6e7c2" />

Deepstream에서 제공되지 않는 플러그인은?

= probe : GStreamer의 기능 중 하나로, 버퍼에 접근하거나 중간에서 데이터를 모니터링하는 데 사용되지만, DeepStream의 플러그인 명칭으로 사용되지는 않는다

> source : 영상입력

> decoding, encoding : 디코딩, 인코딩

> inference : 추론 실행

>  sink : 출력 장치로 보낸다

epStream은 NVIDIA에서 개발한 AI 기반 비디오 분석 프레임워크로, 
특히 엣지 디바이스나 서버에서 실시간 영상 처리 및 추론을 수행하는 데 최적화되어 있음

| 항목          | 내용                                                     |
| ----------- | ------------------------------------------------------ |
| **제작사**     | NVIDIA                                                 |
| **목적**      | 실시간 비디오 스트림에서 AI 기반 객체 감지, 추적, 분류 등을 수행                |
| **주요 기술**   | GStreamer 기반 파이프라인, TensorRT 추론, Jetson 및 dGPU 지원      |
| **지원 입력**   | 카메라, RTSP, 파일(mp4, avi 등), Kafka 등                     |
| **지원 출력**   | 화면 출력, 파일 저장, 메시지 큐(MQTT, Kafka 등), 클라우드 전송            |
| **활용 분야**   | 스마트 시티, 교통 감시, 리테일 분석, 공장 자동화, 보안 시스템 등                |
| **주요 컴포넌트** | Source, Decoder, Inference, Tracker, Analytics, Sink 등 |

<img width="877" height="321" alt="image" src="https://github.com/user-attachments/assets/3b8da68b-2f12-42c5-b7f2-843eda052d52" />

GStreamer 기반인 DeepStream에서 Elements는 핵심 구성 요소가 맞지만, Caps(Capabilities), Pads, Buffers 등이 함께 동작하며 파이프라인을 구성. 따라서 "core building blocks"이라는 표현은 모든 역할을 Elements만 한다는 오해를 불러일으킬 수 있는 부정확한 설명



<img width="874" height="286" alt="image" src="https://github.com/user-attachments/assets/9ec9cb74-10b0-4d95-a53c-c5f1d5f47d8b" />

→ 하드웨어 사용률과 메모리 점유율은 ‘높으면 안 됨’,

→ 오히려 낮고 효율적으로 사용하는 것이 이상적임.

→ 즉, "high"가 아니라 "low" or "optimized"가 되어야 맞는 문장

<img width="888" height="345" alt="image" src="https://github.com/user-attachments/assets/03150408-cc03-4156-9e82-c81b80b34fac" />

DeepStream을 실시간 비디오 AI 애플리케이션에 사용하는 장점은 무엇

✅ 정답: 모두 해당됩니다
✅ Includes various hardware accelerated plugins for encoding/decoding, AI inference, scaling, and conversion.
→ DeepStream은 NVIDIA GPU의 성능을 활용하여 다양한 하드웨어 가속 플러그인을 제공합니다.

✅ Uses a plugin architecture which enables flexibility to develop highly-performant applications with different input and output requirements.
→ GStreamer 기반의 플러그인 구조는 다양한 입출력에 맞춰 유연하게 구성할 수 있습니다.

✅ Provides compatibility with state-of-the-art video AI models.
→ YOLO, SSD, Faster R-CNN, PeopleNet 등 최신 AI 모델과의 호환성 제공.

✅ Supports remote management for deployment in any cloud and at the edge.
→ DeepStream은 클라우드 및 엣지 환경 모두에서 배포 및 원격 관리를 지원합니다. (예: NVIDIA Fleet Command)


