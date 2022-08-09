# ROS2 통신

# VMWARE 16 PLAYER 와 Rasberypi4 간의 ROS2 통신

 1 PC 네트워크 VMWARE BRIDGE PROTOCOL, 브리지 드라이버 체크
 
 2 VMWARE Machine Settings
  - VMWARE Machine Settings -> NetworkAdapter -> Bridged Check
 
 3 openssh-server 설치
  - sudo apt update
  - sudo apt install openssh-server
  - sudo systemctl status ssh (서비스 구동 확인)
  - sudo ufw allow ssh (방화벽 허용)
 
 4 ROS2_DOMAIN_ID 설정
  - sudo nano ~/.bashrc 
  - export ROS_DOMAIN_ID = [숫자]
  
  

  
# 미들웨어 rmw_fastrtps 설치
  
 1 apt 저장소 설치
  - sudo apt install ros-foxy-rmw-fastrtps-cpp 
   
 2 ROS2 워크스페이스 source 폴더에 Fast DDS, rmw_fastrtps clone
  - cd 워크스페이스/src
  - git clone https://github.com/ros2/rmw_fastrtps ros2/rmw_fastrtps
  - git clone https://github.com/eProsima/Fast-DDS eProsima/fastrtps
     
 3 Fast DDS 필요한 패키지 설치 
  - cd ..
  - rosdep install --from src -i
  
 4 colcon 빌드
  - colcon build --symlink-install
  
 5 환경변수 지정
  - source ~/.bashrc
  - export RMW_IMPLEMENTATION=rmw_fastrtps_cpp
