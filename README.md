# EdgeNode C-Track ROS Bags

MORAI C-Track에서 기록한 EdgeNode 자율주행 개발용 ROS 2 bag 데이터입니다.

## Environment

- Simulator: MORAI
- Map: C-Track
- ROS 2: Humble
- Storage: sqlite3

## Camera configuration

- X: 0.62 m
- Y: 0.00 m
- Z: 0.59 m
- Roll: 0 deg
- Pitch: 10 deg
- Yaw: 0 deg
- Camera rate: approximately 30 FPS

## c_track_perception

카메라 기반 인지 알고리즘 개발용 데이터입니다.

- Duration: 118.24 sec
- Size: approximately 251 MiB

Topics:

- /camera/image/compressed
- /camera/image/compressed/info
- /ego_vehicle_status

## c_track_full

Localization, EKF, Planning, Perception 통합 개발용 데이터입니다.

- Duration: 106.10 sec
- Size: approximately 673 MiB

Topics:

- /camera/image/compressed
- /camera/image/compressed/info
- /gps
- /Imu
- /lidar/points
- /ego_vehicle_status
- /object_status
- /traffic_light_status
- /intersection_status
- /collision_data
- /tf

## Playback

EdgeNode Docker container 안에서 ROS 2 환경을 source 한 뒤 재생합니다.

Perception bag:

ros2 bag play c_track_perception --loop

Full bag:

ros2 bag play c_track_full --loop

MORAI 전용 메시지 타입을 확인할 때는 morai_ros2_msgs가 설치된 EdgeNode Docker 환경을 사용합니다.
