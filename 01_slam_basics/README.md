# SLAM 기본 개념

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
- 

---

## 📚 참고 자료
- [ROS2 Slam Toolbox](https://github.com/SteveMacenski/slam_toolbox)  
