

## 1. gazebo 실행이 안되는 문제

```
# gazebo 실행
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
```

<details>
<summary>내용보기 🔽</summary>

#### 🔹 에러 분석

```
[ERROR] [gzserver-1]: process has died [pid 22064, exit code 255, cmd 'gzserver /opt/ros/humble/share/turtlebot3_gazebo/worlds/turtlebot3_world.world -slibgazebo_ros_init.so -slibgazebo_ros_factory.so -slibgazebo_ros_force_system.so'].
```
- `gzserver`: Gazebo 시뮬레이션 서버 프로세스
- `exit code 255`: 일반적으로 Gazebo가 world 파일을 로드할 수 없거나 라이브러리 로딩 실패
- `slibgazebo_ros_*.so`: ROS2와 Gazebo를 연결하는 플러그인 로딩

즉, Gazebo 자체가 실행되지 않거나 world/플러그인을 로드하지 못함이 원인.

#### 🔹 해결 방법

```
# ~/.bashrc 파일에 환경변수 설정추가

export GAZEBO_MODEL_PATH=/usr/share/gazebo-11/models:/opt/ros/humble/share/turtlebot3_gazebo/models
```

```
# 패키지 삭제 후 재설치
sudo apt remove ros-humble-turtlebot3-gazebo ros-humble-turtlebot3-simulations
sudo apt update
sudo apt install ros-humble-turtlebot3-gazebo ros-humble-turtlebot3-simulations
```

</details>

---

## 1-1. gazebo 실행이 안되는 문제 (환경변수 꼬임)

<details>
<summary>내용보기 🔽</summary>


#### 🔹 에러 분석

```
[INFO] [spawn_entity.py-4]: process has finished cleanly [pid 9887] [gzclient-2] gzclient: /usr/include/boost/smart_ptr/shared_ptr.hpp:728: typename boost::detail::sp_member_access<T>::type boost::shared_ptr<T>::operator->() const [with T = gazebo::rendering::Camera; typename boost::detail::sp_member_access<T>::type = gazebo::rendering::Camera*]: Assertion px != 0' failed. [ERROR] [gzclient-2]: process has died [pid 9883, exit code -6, cmd 'gzclient --gui-client-plugin=libgazebo_ros_eol_gui.so'].

```

#### 🔹 해결 방법

```
cd ~
mkdir -p ros2_ws/src
cd ros2_ws
sudo apt update
sudo apt install ros-humble-gazebo-ros-pkgs ros-humble-gazebo-ros
cd ~/ros2_ws
colcon build
source install/setup.bash
echo $GAZEBO_RESOURCE_PATH
# 만약 비어있으면
export GAZEBO_RESOURCE_PATH=/usr/share/gazebo-11:~/ros2_ws/install/share
cd ~/ros2_ws
colcon build --packages-select gazebo_ros
source install/setup.bash
```
</details>