# Head Pose Estimation

## 목적
- 사용자의 얼굴을 웹캠을 이용해 실시간으로 입력받음
- Roll, Pitch, Yaw를 이용한 3D 방향값 도출
- 사용할 환경에 가장 적합한 최적의 모델을 찾는 과정
- Use for Metaverse - 시선 처리

## Models
### 1. HopeNet(https://github.com/natanielruiz/deep-head-pose)
- 300W-LP 데이터셋으로 학습된 모델
- Pytorch & OpenCV
- Simple, 다소 불안정한 result

### 2. WHENet(https://github.com/Ascend-Research/HeadPoseEstimation-WHENet)
- RGB 이미지에서 오일러 각(Roll, Pitch, Yaw) 값을 계산
- YOLO_v3 를 이용한 Face Detection
- Problem : Version 문제(Tensorflow-gpu)

<img src="https://user-images.githubusercontent.com/62232217/148342110-e2c43c5e-8cb7-4244-b8ca-b97141dce0df.gif"  width="400" height="300"/>


### 3. Simple OpenCV Head Pose Estimation(https://github.com/by-sabbir/HeadPoseEstimation)
- Simple model
- Left, Right, Forward 단순 결과
- Problem : 각도 범위가 조금만 커져도 매우 불안정함

<img src="https://user-images.githubusercontent.com/62232217/148343236-fb881279-5ba3-4367-95fc-79811f9f0be0.jpg"  width="300" height="240"/> <img src="https://user-images.githubusercontent.com/62232217/148343233-2faf9e01-c558-48a0-9a03-f6a83596ad1f.jpg"  width="300" height="240"/> <img src="https://user-images.githubusercontent.com/62232217/148343237-21f93fa8-4ee3-4c13-8eee-e83355b08b67.jpg"  width="300" height="240"/>

### 4. Deepgaze(https://github.com/mpatacchiola/deepgaze)
- 3개의 축을 명확히 확인 가능
- Problem : 각도 범위 매우 한정적, 얼굴 인식 자체의 불안정
