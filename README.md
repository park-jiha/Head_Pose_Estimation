# Head Pose Estimation

## 목적
- 사용자의 얼굴을 웹캠을 이용해 실시간으로 입력받음
- Roll, Pitch, Yaw를 이용한 3D 방향값 도출
- Use for Metaverse

## Models
### 1. HopeNet(https://github.com/natanielruiz/deep-head-pose)
- 300W-LP 데이터셋으로 학습된 모델
- Pytorch & OpenCV
- Simple, 다소 불안정한 result

### 2. WHENet(https://github.com/Ascend-Research/HeadPoseEstimation-WHENet)
- RGB 이미지에서 오일러 각(Roll, Pitch, Yaw) 값을 계산
- YOLO_v3 를 이용한 Face Detection
- Problem : Version 문제(Tensorflow-gpu)

![whenet](https://user-images.githubusercontent.com/62232217/148342110-e2c43c5e-8cb7-4244-b8ca-b97141dce0df.gif)

### 3. Simple OpenCV Head Pose Estimation(https://github.com/by-sabbir/HeadPoseEstimation)
- Simple model
- Left, Right, Forward 단순 결과
- Problem : 각도 범위가 조금만 커져도 매우 불안정함



### 4. 
