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

<img src="https://user-images.githubusercontent.com/62232217/148343236-fb881279-5ba3-4367-95fc-79811f9f0be0.jpg"  width="260" height="200"/> <img src="https://user-images.githubusercontent.com/62232217/148343233-2faf9e01-c558-48a0-9a03-f6a83596ad1f.jpg"  width="260" height="200"/> <img src="https://user-images.githubusercontent.com/62232217/148343237-21f93fa8-4ee3-4c13-8eee-e83355b08b67.jpg"  width="260" height="200"/>

### 4. Deepgaze(https://github.com/mpatacchiola/deepgaze)
- 3개의 축을 명확히 확인 가능
- Problem : 각도 범위 매우 한정적, 얼굴 인식 자체의 불안정

<img src="https://user-images.githubusercontent.com/62232217/148345234-cfc69e22-0d72-4de7-a921-4ea17274e3a7.jpg"  width="250" height="200"/>  <img src="https://user-images.githubusercontent.com/62232217/148345238-edfc1817-74f5-4c81-b0a0-8983e5c93c18.jpg"  width="250" height="200"/> <img src="https://user-images.githubusercontent.com/62232217/148345242-f41948c0-b354-4426-8a92-9b47f03e033b.jpg"  width="250" height="200"/>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://user-images.githubusercontent.com/62232217/148345237-ef10dd10-ec2e-44c0-8450-06f2f5970033.jpg"  width="250" height="200"/> <img src="https://user-images.githubusercontent.com/62232217/148345240-3d272a54-51f5-42a3-982d-1ef4368f6455.jpg"  width="250" height="200"/>

### 5. FSA-Net(https://github.com/shamangary/FSA-Net)
- Keras & Tensorflow
- Problem : Version 문제(Tensorflow-gpu)

### 6. Face Pose with Retina Face(https://github.com/fisakhan/Face_Pose)
- Tensorflow 2.x.x
- 인식률 좋음(전신이 나오는 frame 환경에서도 안정적)
- 높은 정확도
#### ※ Range
Roll: -x to x (0 is frontal, positive is clock-wise, negative is anti-clock-wise)<br>
Yaw: -x to x (0 is frontal, positive is looking right, negative is looking left)<br>
Pitch: 0 to 4 (0 is looking upward, 1 is looking straight, >1 is looking downward)<br>

<img src="https://user-images.githubusercontent.com/62232217/148650217-f87f2079-065c-46b1-b9ef-5d8e2e79460a.png"  width="250" height="200"/>  <img src="https://user-images.githubusercontent.com/62232217/148650224-6df0f88e-1d03-4d8d-a813-274c2579e60d.png"  width="250" height="200"/> <img src="https://user-images.githubusercontent.com/62232217/148650227-3c15467b-7616-42ae-8ab8-55dd3798c98e.png"  width="250" height="200"/>

<img src="https://user-images.githubusercontent.com/62232217/148650229-334d8be0-7660-46d7-abe2-ab2c2634d08b.png"  width="250" height="200"/>  <img src="https://user-images.githubusercontent.com/62232217/148650232-4b7b6da4-d4b0-4f1d-80a6-c19e845a6f83.png"  width="250" height="200"/> <img src="https://user-images.githubusercontent.com/62232217/148650234-fcae35a5-508c-4618-9022-c5fb15c6c51f.png"  width="250" height="200"/>

<img src="https://user-images.githubusercontent.com/62232217/148650243-be07c434-ecab-4061-b625-b83f173ad1ab.png"  width="250" height="200"/>  <img src="https://user-images.githubusercontent.com/62232217/148650246-a8e1b113-e16f-4537-8482-7f24b62bdba2.png"  width="250" height="200"/> <img src="https://user-images.githubusercontent.com/62232217/148650250-782c8d2f-4677-4da5-8dbc-eb8e871518e7.png"  width="250" height="200"/>

- 먼거리 인식률 확인(+ 밝을 때, 어두울 때) → 빛이 강하게 내리쬐는 경우 아니면 잘 인식함

<img src="https://user-images.githubusercontent.com/62232217/148655691-5b3845df-62ab-44ae-8ffb-b9227bad9f22.png"  width="300" height="220"/>  <img src="https://user-images.githubusercontent.com/62232217/148655693-9a31a129-3a54-4f98-9b11-aa6853933d6d.png"  width="300" height="220"/>

- 모자 착용 시 & 마스크 → 얼굴을 거의 다 가리지 않는 범위에서는 꽤 정확하게 인식함

<img src="https://user-images.githubusercontent.com/62232217/148655735-5eeb723e-f071-4514-a994-328d332c5690.png"  width="250" height="200"/>  <img src="https://user-images.githubusercontent.com/62232217/148655736-bb089acf-711d-4876-92b1-f04bd79dce99.png"  width="250" height="200"/> <img src="https://user-images.githubusercontent.com/62232217/148655738-6537dd65-67ce-4f3d-a8d1-ea704b1f56c0.png"  width="250" height="200"/>

- 마스크 (+모자) → 마스크 인식률 훌륭하고, 마스크+모자일때는 아주 약간 차이가 눈에 보임

<img src="https://user-images.githubusercontent.com/62232217/148655777-6ffcaf19-1bb1-4640-a867-ac155457ea1c.png"  width="300" height="220"/>  <img src="https://user-images.githubusercontent.com/62232217/148655778-6628c7e9-6610-4c12-b8db-9b17d229d08e.png"  width="300" height="220"/>

- 전체적인 시연 영상

<img src="https://user-images.githubusercontent.com/62232217/148342110-e2c43c5e-8cb7-4244-b8ca-b97141dce0df.gif"  width="400" height="300"/>
![image](https://user-images.githubusercontent.com/62232217/148656865-02dc2cde-5e4b-4a01-8800-f7423e02b88d.png)
