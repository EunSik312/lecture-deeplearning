
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/5bfba382-3035-448b-b79d-4323c67accfa" />

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/54b5d024-f48d-4deb-8f5e-2fc1b0c98b47" />

런포드 연결할 때 파이토치 버전 확인하고 주피터 노트북이 나오는지 확인해야 연결가능
파이토치 버전은 2.8이어야 연결이 가능 

이것을 어떤 PIP 라이브러리를 사용할 것인지 

파이토치 트래픽넷을 이용한 자율주행 코드 작성

런포드에서 3090 실행

파이토치와 텐서알티의 비

파이썬 런처 들어가면 노트북의 파이썬을 실행하고 우클릭으로 이름을 바꾼다\

#GPT답
RTX 3090을 사용하면 GPU 가속을 활용할 수 있기 때문에, CUDA와 PyTorch GPU 버전이 제대로 설치되어야 합니다. 또한, 트래픽넷과 관련된 라이브러리도 필요할 것입니다.

RTX 3090을 활용하려면 PyTorch가 GPU를 사용할 수 있도록 설정해야 합니다. 이를 위해 CUDA가 설치되어야 합니다. NVIDIA에서 CUDA Toolkit을 설치하고, PyTorch에서 GPU 버전을 사용하도록 설정합니다.

데이터셋: 자율주행에서는 TrafficNet 외에도 KITTI, Cityscapes, Waymo 등 다른 유명한 자율주행 데이터셋도 많이 사용됩니다.

모델 최적화: RTX 3090을 활용하는 만큼, 모델을 최적화하여 빠르게 학습하고 추론할 수 있도록 해야 합니다. Mixed Precision Training 같은 기술을 사용할 수 있습니다.

경로 계획: 경로 계획이나 제어를 다루는 알고리즘 (예: DQN, A3C, PPO 등)을 추가하여 더욱 복잡한 자율주행 시스템을 만들 수 있습니다.



웹터미널?


<RUNPOD 접속>
https://www.runpod.io/ --> 로그인 --> 교수님이 만드신 팀명: (Pod name)KCCICN (초대받아야 함) --> 초대링크 받고 가입되면 --> 좌측 상단의 자신의 아이이를 클릭하면 초대받은 POD(KCCICN@gmaill)가 보임
* 작업환경: 좌측메뉴의 'POD'중  RTX 3090
* RUNPOD를 사용하는 이유
- 고사양 주피터 노트북이나 서버급 PC를 사용해야 하는 경우 이러한 환경을 제공하는 runpod에서 작업가능 
