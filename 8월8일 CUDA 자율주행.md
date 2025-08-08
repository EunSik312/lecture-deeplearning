
}
# CUDA

어떻게 빠르게 처리하는지, 자율주행의 실시간 인지를 가능하계하는 gpu

파이썬을 gpu에서 실행하는 가장 쉬운 방법은 Numba
<img width="931" height="247" alt="image" src="https://github.com/user-attachments/assets/89513850-cdde-420b-aac8-a3f141a4bf44" />

<img width="688" height="404" alt="image" src="https://github.com/user-attachments/assets/e1a61173-fc9c-43b4-ada6-fc17b9c2d9e1" />
Numba가 GPU가 계산할 수 있는 코드로 변환해주는데 전부 다 해주지는 않는다

target에 CPU를 넣으면 CPU를 사용한다 target에 CUDA를 넣으면 CUDA를 사용한다

C++, Python, C

<img width="712" height="512" alt="image" src="https://github.com/user-attachments/assets/49f09bfe-9b00-495d-9112-3c0be74f014c" />

<img width="670" height="181" alt="image" src="https://github.com/user-attachments/assets/f74bcffc-ca92-4fb2-b3aa-7641adf4f2b6" />

numab cuda를 설치 해야함
<img width="529" height="93" alt="image" src="https://github.com/user-attachments/assets/7b06396d-b71f-4849-8010-e3e500ae7690" />
https://github.com/googlecolab/colabtools/issues/5081#issuecomment-2629611179

# CUDA (쿠다) 란 무엇인가?
## 1. 한 줄 정의

NVIDIA(엔비디아)가 개발한 GPU(그래픽카드)용 병렬 컴퓨팅 플랫폼이자 프로그래밍 모델입니다.

즉, GPU의 수많은 코어를 활용하여 그래픽 작업뿐만 아니라, 복잡하고 방대한 일반 계산을 초고속으로 처리할 수 있게 해주는 기술입니다.


## 2. 핵심 개념: 왜 GPU를 사용하는가? (CPU vs GPU 비유)

CUDA를 이해하려면 CPU와 GPU의 역할 차이를 아는 것이 중요합니다.

CPU (Central Processing Unit): 소수의 유능한 전문가

매우 복잡하고, 순서가 중요한 작업을 처리하는 데 특화되어 있습니다.

코어(일꾼)의 수가 적지만, 각 코어의 성능이 매우 뛰어납니다.

비유: 어려운 문제를 순서대로 풀어내는 소수의 박사 그룹.

GPU (Graphics Processing Unit): 수천 명의 단순 작업자

단순하고 반복적인 작업을 동시에 처리하는 데 특화되어 있습니다.

코어의 수는 수백, 수천 개에 달하지만, 각 코어는 비교적 단순한 작업만 수행합니다.

비유: 단순 덧셈만 할 줄 아는 수천 명의 아르바이트생. 1,000개의 덧셈 문제를 동시에 풀어버립니다.

CUDA는 바로 이 **수천 명의 단순 작업자(GPU 코어)에게 일을 효율적으로 나누어 주고, 동시에 처리하도록 지시하는 '작업 지시서'이자 '시스템'**이라고 할 수 있습니다.


## 3. CUDA가 제공하는 것들

CUDA는 단순히 개념만 있는 것이 아니라, 실제 개발을 위한 도구들을 포함합니다.

프로그래밍 환경 (CUDA Toolkit):

개발자가 GPU의 동작을 직접 제어할 수 있는 CUDA C/C++ 언어 확장 기능.

코드를 컴파일하는 컴파일러(nvcc) 및 디버깅 도구.

각종 전문 라이브러리:

cuDNN: 딥러닝(AI) 연산을 위한 라이브러리.

cuBLAS: 행렬 연산 등 선형대수를 위한 라이브러리.

cuFFT: 고속 푸리에 변환을 위한 라이브러리.

드라이버와 API:

응용 프로그램이 GPU 하드웨어와 통신할 수 있게 해주는 통로.


## 4. 왜 중요한가?

압도적인 성능 향상: 인공지능(AI) 학습, 대규모 데이터 분석, 과학 시뮬레이션 등 방대한 연산이 필요한 작업의 속도를 수십 배에서 수백 배까지 높여 현대 컴퓨팅의 발전을 이끌고 있습니다.

개발 생태계와 접근성: 과거에는 C++ 전문가만 다룰 수 있었지만, 이제는 Numba, PyTorch, TensorFlow와 같은 파이썬 라이브러리를 통해 훨씬 쉽게 CUDA의 강력한 성능을 활용할 수 있게 되었습니다.

<img width="977" height="174" alt="image" src="https://github.com/user-attachments/assets/594b82d4-cf68-4fcc-a0d2-24e0b25e646e" />

nsys 설치 

!apt update
!apt install -y --no-install-recommends gnupg
!echo "deb http://developer.download.nvidia.com/devtools/repos/ubuntu$(source /etc/lsb-release; echo "$DISTRIB_RELEASE" | tr -d .)/$(dpkg --print-architecture) /" | tee /etc/apt/sources.list.d/nvidia-devtools.list
!apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/7fa2af80.pub
!apt update
!apt install nsight-systems-cli

<img width="977" height="407" alt="image" src="https://github.com/user-attachments/assets/7c046932-7731-4407-84c2-00d4bee0ad68" />

