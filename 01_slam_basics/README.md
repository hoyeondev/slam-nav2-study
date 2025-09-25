# SLAM 기본 개념

## 📌 ICP(Iterative Closest Point)란?

두 개의 점군(Point Cloud) 데이터를 비교해서, 한 쪽을 다른 쪽에 맞게 정렬(정합, registration)하는 알고리즘
예: 로봇이 지금 라이다로 스캔한 점군 vs. 기존 지도 점군 → 두 점군을 최대한 겹치도록 위치/자세(x, y, θ)를 보정

### 1. SLAM(지도 작성)
- Gmapping, Cartographer, Karto 같은 SLAM 알고리즘 내부에서 scan matching 단계에 ICP 또는 ICP 변형(NDT, GICP 등)을 사용
- 라이다 스캔을 이어붙여 지도를 만드는 과정에서 로봇의 상대 위치를 추정할 때 쓰임

### 2. Localization(위치 추정, AMCL 대안)
- 이미 완성된 지도에서 로봇이 현재 어디 있는지 추정할 때, 라이다 스캔 vs. 지도 기반 스캔을 ICP로 맞추어 위치 오차를 줄일 수 있다.
- 예: 로봇이 Nav2로 목적지까지 가는 도중 → "내가 지도에서 어느 좌표에 있지?" → ICP를 써서 라이다 데이터와 지도 점군을 정합

---

## 1. SLAM의 정의와 필요성
- **SLAM (Simultaneous Localization and Mapping)**:  
  로봇이 **자신의 위치를 추정(Localization)**하면서 동시에 **주변 환경의 지도(Map)를 작성**하는 기술.  
- 필요성: GPS가 불가능한 실내/터널/우주 공간에서 로봇이 자율적으로 움직이기 위해 필수적임.

---

## 2. LiDAR 기반 SLAM vs 비전 기반 SLAM
### LiDAR 기반
- 원리: 레이저 스캐너로 거리 측정 → 2D/3D 점군(Point Cloud) 생성  
- 장점: 높은 정밀도, 조명 변화에 강함  
- 단점: 센서 가격이 비쌈, 유리/반사 물체에 약함  
- 대표 알고리즘: **GMapping, Hector SLAM, Cartographer**

### 비전 기반 (Visual SLAM)
- 원리: 카메라 영상에서 특징점(Feature) 추출 → 연속된 프레임 간 매칭  
- 장점: 센서 저렴, 풍부한 시각 정보(객체 인식과 결합 가능)  
- 단점: 조명·환경 변화에 민감, 연산량 많음  
- 대표 알고리즘: **ORB-SLAM, LSD-SLAM, RTAB-Map**

---

## 3. 2D SLAM vs 3D SLAM
### 2D SLAM
- 주로 LiDAR 2D 센서 사용  
- 평면 지도 생성  
- 실내 로봇(청소기, 배달 로봇)에 주로 활용

### 3D SLAM
- 3D LiDAR, RGB-D 카메라 사용  
- 점군 기반의 3차원 지도 작성  
- 드론, 자율주행차, 정밀 매핑에 활용  
- 연산량 크고 하드웨어 요구사항 높음

---

## 4. 학습 메모
- SLAM은 **센서 종류 + 차원(2D/3D)** 에 따라 접근 방식이 다름.

#### 구조
- Gazebo simulation
  → 시뮬레이터에서 로봇/센서/환경을 가상으로 돌리는 영역
- Mapping (SLAM)
  → 센서 데이터를 모아 지도를 만드는 알고리즘/노드 영역
- Nav2 (Navigation2)
  → 지도 위에서 경로 계획, 경로 추종, 회피 등을 담당하는 영역
- CycloneDDS (rmw-cyclonedds-cpp)
  → 위 세 가지 모두가 서로 데이터를 주고받을 때 사용하는 통신 미들웨어

---

## 📚 참고 자료
- [ROS2 Slam Toolbox](https://github.com/SteveMacenski/slam_toolbox)  
