---
description: 이미지 클릭 시 확대가 가능하여 크게 보실 수 있습니다.
---

# STELLA N1 Pi Camera Module V2 설치 및 구동하기

원하는 ROS 버전에 맞게 설치 후 메뉴의  ROS 버전을 확인 하면서 진행 하시면 됩니다. rc/



```
 (SSH 접속 후) cd ~/catkin_ws/src/STELLA_JETSON_NANO/stella_camera/src/
 chmod +x stella_camera.py
```



* camera 패키지를 실행합니다.

```
(SSH 접속 후) roslaunch stella_camera stella_camera.launch
roscore
rqt_image_vies /camera
```

![](../../.gitbook/assets/059.png)

* [ ] UI 이용 camera 실행&#x20;
* [ ] camera 기능이 추가된 UI를 다운로드 후, 컴파일을 진행합니다.

```
cd ~/catkin_ws/src/
git clone https://github.com/ntrexlab/STELLA_UI_CAMERA.git
cd ~/catkin_ws/src/STELLA_UI_CAMERA/scripts/
chmod +x stella_ui_dialog.pyc
cd ~/catkin_ws/
catkin_make
```

* 하기의 명령어를 통해 STELLA\_UI\_CAMERA를 실행합니다.&#x20;

```
roslaunch stella_ui_camera stella_ui_camera.launch
```

![](../../.gitbook/assets/060.png)

*   기의 그림에 표시되어 있는 부분을 통하여, Remote PC와 Robot(STELLA N1)의 IP,

    &#x20;Robot의 ID와 패스워드를 입력한 후, Camera Connect 버튼을 클릭합니다.&#x20;

![](../../.gitbook/assets/061.png)

* 충분한 시간이 흐른 후 Camera Show 버튼을 클릭하면, 카메라 영상을 받아보실 수 있습니다.

![](../../.gitbook/assets/062.png)
