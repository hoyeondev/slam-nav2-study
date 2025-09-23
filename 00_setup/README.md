

## 환경 세팅

```bash
# Nav2 및 TurtleBot3 관련 패키지 설치
# - ros-humble-navigation2 : ROS2 Navigation2 패키지 (경로 계획, 제어 등)
# - ros-humble-nav2-bringup : Nav2 실행을 위한 기본 bringup 설정/launch 파일 모음
# - ros-humble-turtlebot3* : TurtleBot3 관련 모든 패키지(* = wildcard, 예: turtlebot3_bringup, turtlebot3_navigation2 등)
sudo apt install ros-humble-navigation2 ros-humble-nav2-bringup ros-humble-turtlebot3*

# colcon 빌드 도구 확장 설치
# - colcon은 ROS2에서 워크스페이스를 빌드할 때 사용하는 표준 툴
# - python3-colcon-common-extensions : colcon의 자주 쓰는 확장 기능 모음
sudo apt install python3-colcon-common-extensions

# VS Code 설치
# - Snap 패키지 관리자를 통해 설치
# - --classic 옵션 : 개발 툴 특성상 시스템 전체 접근 권한 필요
sudo snap install code --classic

# VS Code 실행
# - 설치 후 "code" 명령으로 실행 가능
code

```