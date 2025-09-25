
## 🖥 ROS2 + TurtleBot3 + Gazebo 환경에서 SLAM 실습


### 1. Gazebo 시뮬레이션 실행
```bash
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
```
### 2. Cartographer SLAM 실행 (시뮬레이터 시간 사용)
```bash
ros2 launch turtlebot3_cartographer cartographer.launch.py use_sim_time:=True
```
- Cartographer SLAM 노드 실행
- LiDAR 데이터를 기반으로 지도 작성 및 로봇 위치 추정
- Gazebo 시뮬레이터에서 제공하는 시간(/clock)을 사용하도록 설정

### 3. 키보드 조작 (Teleop)
```bash
ros2 run turtlebot3_teleop teleop_keyboard
```

### 4. 맵 저장
```bash
ros2 run nav2_map_server map_saver_cli -f maps/my_map
```