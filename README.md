# Smart Bug Trap

## 🐞 프로젝트 개요
Smart Bug Trap은 **딥러닝(YOLO)과 초음파 센서를 활용하여 초파리, 모기, 바퀴벌레를 탐지**하고, 특정 유인제를 분사한 후 **10cm 이내 접근 시 문을 닫고 살충제를 분사**하는 스마트 해충 포획 시스템입니다. 

## 🚀 주요 기능
- **YOLO 모델을 활용한 실시간 해충 탐지** (초파리, 모기, 바퀴벌레 분류)
- **초음파 센서로 거리 측정** (1m 이내 유인제 분사, 10cm 이내 문 닫기 및 살충제 분사)
- **Raspberry Pi 4B 및 OpenCV 적용**
- **카메라 모듈 2를 이용한 이미지 처리**

## 🛠 설치 방법
```bash
# Raspberry Pi에 필수 패키지 설치
sudo apt update && sudo apt upgrade -y
sudo apt install python3-pip
pip install opencv-python numpy torch torchvision

# YOLO 모델 다운로드 및 환경 설정
git clone https://github.com/ultralytics/yolov5.git
cd yolov5
pip install -r requirements.txt

# Smart Bug Trap 코드 다운로드
git clone https://github.com/사용자명/smart-bug-trap.git
cd smart-bug-trap
```

## 🎯 사용법
```bash
# YOLO 모델 실행
python detect.py --source 0 --weights best.pt --conf 0.5

# 초음파 센서 및 분사 시스템 실행
python smart_bug_trap.py
```

## 🏗 시스템 구성
- **Raspberry Pi 4B**: 중앙 제어 장치
- **Camera Module 2**: 실시간 영상 수집
- **YOLOv5**: 해충 탐지 및 분류
- **초음파 센서**: 거리 측정
- **서보 모터**: 문 닫기 및 분사 시스템 작동
