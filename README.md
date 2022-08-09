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
  
