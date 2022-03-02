# ROS 1 - STELLA N1 Pi Camera Module V2 설치 및 구동하기



* ROS 경우 <mark style="color:red;">**네트워크를 통한 통신을**</mark> 기반으로 구현되어 있기 때문에 <mark style="color:red;">**원격 PC 와 SBC가 동일 Wifi 네트워크 망에 연결 되어 있으며 인터넷도 정상 작동하는지 확인 후 진행합니다.**</mark>    &#x20;

<!---->

* [ ] Pi Camera Module V2 연결

![](../../.gitbook/assets/057.png)

* [ ] 싱글보드 Bluetooth 설정 (Raspberry Pi 버전만 실행)

<!---->

* <mark style="color:red;">**원격PC 새로운 터미널**</mark>에서 SSH로 SBC에 접속합니다.

```
ex) ssh pi@192.168.0.xxx 입력 후 패스워드 입력
```

* <mark style="color:red;">**위 빨간 글 SSH 접속 터미널**</mark>에서 하기 명령어를 입력합니다. &#x20;

```
sudo apt-get update && sudo apt-get upgrade
```

* &#x20;<mark style="color:red;">**위 빨간 글 SSH 접속 터미널**</mark>에서 하기 명령어를 입력합니다.&#x20;

```
sudo raspi-config
```

![](../../.gitbook/assets/058.png)

* [ ] 설치 &#x20;

<!---->

* camera 패키지를 실행하기 위한 기본 설정을 진행합니다.&#x20;
* <mark style="color:red;">**원격PC 새로운 터미널**</mark>에서 SSH로 SBC에 접속합니다.

```
ex) ssh ntrex@192.168.0.xxx 입력 후 패스워드 입력
```

1. &#x20;SBC가 <mark style="color:blue;">**Raspberry Pi**</mark> 인 경우&#x20;

* <mark style="color:red;">**위 빨간 글 SSH 접속 터미널**</mark>에에서 명령어를 입력합니다. &#x20;

```
cd ~/catkin_ws/src/STELLA_RASPBERRYPI/stella_camera/src/
chmod +x stella_camera.py
```

2\.   SBC가 <mark style="color:blue;">**Jetson Nano**</mark>인 경우&#x20;

* <mark style="color:red;">**위 빨간 글 SSH 접속 터미널**</mark>에에서 명령어를 입력합니다.

```
 cd ~/catkin_ws/src/STELLA_JETSON_NANO/stella_camera/src/
 chmod +x stella_camera.py
```

* [ ] 실행

<!---->

* <mark style="color:blue;">**원격 PC에서 터미널**</mark> 실행 후 roscore 실행합니다.

```
roscore
```

* [ ] STELLA N1 구동 파일 실행&#x20;

<!---->

* <mark style="color:red;">**원격PC 새로운 터미널**</mark>에서 SSH로 SBC에 접속합니다.

```
ex) ssh ntrex@192.168.0.xxx 입력 후 패스워드 입력
```

* <mark style="color:red;">**위 빨간 글 SSH 접속 터미널**</mark>에서 명령어를 입력합니다. &#x20;

```
roslaunch stella_bringup stella_robot.lau
```

* <mark style="color:green;">**원격PC 새로운 터미널에서**</mark>**  **<mark style="color:red;">****</mark> camera 패키지를 실행합니다.

```
rqt_image_view /camera
```

![](../../.gitbook/assets/059.png)

* [ ] UI 이용 camera 실행&#x20;

<!---->

* <mark style="color:red;">**원격PC 새로운 터미널**</mark>에서 camera 기능이 추가된 UI를 다운로드 후, 컴파일을 진행합니다.

```
cd ~/catkin_ws/src/
git clone https://github.com/ntrexlab/STELLA_UI_CAMERA.git
cd ~/catkin_ws/src/STELLA_UI_CAMERA/scripts/
chmod +x stella_ui_dialog.pyc
cd ~/catkin_ws/
catkin_make
```

* <mark style="color:green;">**원격PC 새로운 터미널**</mark>에서 하기의 명령어를 통해 STELLA\_UI\_CAMERA를 실행합니다.&#x20;

```
roslaunch stella_ui_camera stella_ui_camera.launch
```

![](../../.gitbook/assets/060.png)

*   하기의 그림에 표시되어 있는 부분을 통하여, Remote PC와 Robot(STELLA N1)의 IP,

    &#x20;Robot의 ID와 패스워드를 입력한 후, Camera Connect 버튼을 클릭합니다.&#x20;

![](../../.gitbook/assets/061.png)

* 충분한 시간이 흐른 후 Camera Show 버튼을 클릭하면, 카메라 영상을 받아보실 수 있습니다.

![](../../.gitbook/assets/062.png)
