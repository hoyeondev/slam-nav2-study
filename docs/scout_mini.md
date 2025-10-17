

### 스카우드 미니 노드를 받기 위한 코드
~/.bashrc 파일에 아래 코드 추가

```
export RPLIDAR_MODEL=A1
export ROS_DOMAIN_ID=30
export ROS_LOCALHOST_ONLY=0
export RMW_IMPLEMENTATION=rmw_fastrtps_cpp
source /opt/ros/humble/setup.bash
source ~/ros2_ws/install/setup.bash
```
