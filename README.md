
# SLAM Naviagtion2 Learning Log 📚

## 📅 Contents

### ✅ 00_setup
- 준비 환경 세팅
- Ubuntu 22.04 + ROS2 Humble 설치
- Gazebo / RViz 환경 세팅
- TurtleBot3 시뮬레이터 준비

### ✅ 01_slam_basics
- SLAM 기본개념
- SLAM의 정의와 필요성
- LiDAR 기반 vs 비전 기반 SLAM 비교

### ✅ 02_gazebo_simulation
- 시뮬레이션 환경
- TurtleBot3 + Gazebo 실행
- RViz에서 센서 데이터 시각화
- ros2 launch로 노드 실행법

### ✅ 03_mapping(지도 작성)
- SLAM Toolbox, Cartographer 실습
- rosbag 데이터로 오프라인 맵핑
- map.pgm, map.yaml 생성 과정 기록

### ✅ 04_localization(위치 추정)
- AMCL 원리와 실행 방법
- Particle Filter 개념 정리
- RViz에서 위치 추정 테스트

### ✅ 05_navigation(Nav2)
- Nav2 기본 구조 (BT, planner, controller, recovery)
- global planner vs local planner 차이
- goal pose 지정 → 경로 계획 및 주행 실습