
## 🖥 Navigation2


### 1. CycloneDDS 패키지 다운로드

```bash
sudo apt install ros-humble-rmw-cyclonedds-cpp
```

ROS 2 Humble 환경에서 기본 미들웨어(Fast DDS) 대신 CycloneDDS를 선택적으로 사용할 수 있게 준비

```bash
# ~/.bashrc 파일 수정

export RMW_IMPLEMENTATION=rmw_cyclonedds_cpp

```

❗ `/opt/ros/humble/share/turtlebot3_navigation2/param$ sudo gedit waffle.yaml`
위 경로의 파일에서 `robot_model_type: "nav2_amcl::DifferentialMotionModel"` 이 부분이 다를 경우 수정해야 함.


❗ 세팅 변경 후 reboot 하기

### 2. Gazebo 시뮬레이션 실행
```bash
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py

# vm에서 실행 시 gui없이 실행하는 명령어
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py gui:=false
```

### 3. navigation2 실행

ros2 launch turtlebot3_navigation2 navigation2.launch.py use_sim_time:=True map:=maps/my_map.yaml
