# Pi 4 라이브러리 업데이트

메뉴얼에서는 캡처의 편의를 위해서 SSH 접속을 이용하여 진행하였지만Raspberry Pi에서 직접 진행하셔도 문제 없습니다.​

* SSH 접속 후 패키지 삭제 및 설치
* <mark style="color:red;">**원격 PC에서 터미널**</mark> 실행 후 SSH로 SBC에 접속합니다.

```
ex) ssh pi@192.168.0.xxx 입력 후 패스워드 입력
```

* <mark style="color:red;">**위 빨간 글 SSH 접속 터미널**</mark>에서 기존 라이브러리삭제합니다.

```
sudo rm -r ~/catkin_ws/src/STELLA_RASPBERRYPI
```

* <mark style="color:red;">**위 빨간 글 SSH 접속 터미널**</mark>에서 업데이트된 라이브러리를 다운로드합니다.

```
cd ~/catkin_ws/src
git clone https://github.com/ntrexlab/STELLA_N1_PI_X4_ROS1_v2.0.git
cd ~/catkin_ws/src/STELLA_N1_PI_X4_ROS1_v2.0/stella_teleop_bluetooth/src/
chmod +x stella_teleop_bluetooth.py
```

* <mark style="color:red;">**위 빨간 글 SSH 접속 터미널**</mark>에서 패키지 컴파일합니다.

```
source ~/.bashrc
cd ~/catkin_ws/catkin_make
```

* <mark style="color:red;">**위 빨간 글 SSH 접속 터미널**</mark>에서 Serial 통신설정

```
cd ~/catkin_ws/src/STELLA_N1_PI_X4_ROS1_v2.0/stella_bringupsh create_udev_rules.shls -la /dev
```

* <mark style="color:blue;">**새로운 원격 PC 터미널**</mark>에서 기존 라이브러리를 삭제합니다.

```
sudo rm -r ~/catkin_ws/src/STELLA_REMOTE_PC
```

* <mark style="color:blue;">**위**</mark> <mark style="color:blue;">**원격 PC 터미널**</mark>에서 업데이트된 라이브러리를 다운로드합니다.

```
cd ~/catkin_ws/src
git clone https://github.com/ntrexlab/STELLA_N1_REMOTEPC_X4_ROS1_v2.0.git
cd ~/catkin_ws/src/STELLA_N1_REMOTEPC_X4_ROS1_v2.0/stella_teleop_bluetooth/src/
chmod +x stella_teleop_bluetooth.py
```

* <mark style="color:blue;">**원격 PC 터미널**</mark>에서 패키지를 컴파일 합니다.

```
source ~/.bashrc
cd ~/catkin_ws/catkin_make
```

