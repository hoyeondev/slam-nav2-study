# ROS2 ↔ Spring Boot WebSocket 연동 가이드

## 목적
Spring Boot 서버에서 주문(WebSocket)을 받아 ROS2 노드로 전달.

---

## 구성
1. ROS2: `/scout/assign_order` 구독 노드 실행  
2. rosbridge_server: WebSocket ↔ ROS2 중계  
3. Spring Boot: STOMP WebSocket 수신 후 rosbridge로 전송  

---

## 주요 명령
```bash
# 패키지 설치
sudo apt install ros-humble-rosbridge-server

# ROS2 rosbridge 실행
ros2 launch rosbridge_server rosbridge_websocket_launch.xml

# ROS2 노드 실행
ros2 run scout_robot assign_order_node
