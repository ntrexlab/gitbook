---
description: STELLA N1은 ROS 기반으로 구성된 자율주행 연구용 플랫폼입니다. 원격 PC에 ROS  설치 후 STELLA N1 운용이 가능합니다.
---

# ROS 2 - 원격 PC 설정

* [ ] 원격 PC에서 Ubuntu 설치하기  
* STELLA N1은 Ubuntu 20.04 LTS 버전을 기준으로 제작되었습니다. STELLA N1을 조정할 원격 컴퓨터에서 Ubuntu  20.04 LTS 버전 설치를 권장 드립니다. Ubuntu 설치는 하기의 링크를 참고하여 설치합니다.

{% tabs %}
{% tab title="Ubuntu 설치 방법" %}
[https://ubuntu.com/tutorials/install-ubuntu-desktop](https://ubuntu.com/tutorials/install-ubuntu-desktop)
{% endtab %}

{% tab title="boot USB 제작 방법" %}
[https://linuxhint.com/rufus\_bootable\_usb\_install\_ubuntu\_18-04\_lts/](https://linuxhint.com/rufus_bootable_usb_install_ubuntu_18-04_lts/)
{% endtab %}
{% endtabs %}

* [ ] Ubuntu가 설치된 원격 PC에 ROS 2설치하기
* STELLA N1은 ROS\(Robot Operating System\)을 기반으로 구성된 자율주행 연구용 플랫폼입 니다. 원격 컴퓨터에 ROS 2 설치 후 STELLA N1 운용이 가능합니다. ROS 2 설치는 하기의 명령어를 이용하여 설치합니다. 

```text
wget https://raw.githubusercontent.com/ntrexlab/ROS_INSTALL_SCRIPT/main/install_ros2_foxy.sh&& chmod 755 ./install_ros2_foxy.sh && bash ./install_ros2_foxy.sh
```

* 위 명령어를 이용하지 않고 직접 ROS 2를 설치할 경우, 하기의 링크를 참고하여 설치하여 주십시오.

{% tabs %}
{% tab title="ROS 공식 사이트" %}
[http://docs.ros.org/en/rolling/Installation/Ubuntu-Install-Binary.html](http://docs.ros.org/en/rolling/Installation/Ubuntu-Install-Binary.html)
{% endtab %}
{% endtabs %}

* [ ] ROS 2 설치 확인하기 
* 바탕화면에서 Ctrl + Alt + t를 눌러 Terminal에서 roscore 입력합니다.
* roscore 입력 시 하기의 그림과 같이 동작되면 정상적으로 작동함을 확인할 수 있습니다.

![ ](../../.gitbook/assets/013.png)

* [ ] STELLA N1  필수 ROS 2 Package 설치하기
* Ubuntu 터미널에 apt-get install 명령어를 사용하여 패키지를 설치합니다.

```text
$ sudo apt-get install ros-foxy-cartographer ros-foxy-cartographer-ros ros-foxy-navigation2 ros-foxy-nav2-bringup
```

![ ](../../.gitbook/assets/014.png)

* [ ] STELLA N1 라이브러리 설치하기
* 우선, STELLA 라이브러리 설치를 위해 ROS 2 Workspace 폴더를 생성합니다.

{% tabs %}
{% tab title="ROS2.org" %}
[http://docs.ros.org/en/rolling/Tutorials/Workspace/Creating-A-Workspace.html](http://docs.ros.org/en/rolling/Tutorials/Workspace/Creating-A-Workspace.html)
{% endtab %}
{% endtabs %}

* 일반적으로 사용하는 Workspace 이름인 colcon\_ws를 기준으로, colcon\_ws에 진입하여 git clone을 통해 Stella 라이브러리 다운로드 합니다.

```text
cd ~/colcon_ws/src/
git clone https://github.com/ntrexlab/STELLA_REMOTE_PC_ROS2.git
```

* 다운로드 된 라이브러리는 catkin\_make를 통해 컴파일 합니다.

```text
cd ~/colcon_ws/src/STELLA_REMOTE_PC_ROS2/stella_teleop/stella_teleop/script/
chmod +x teleop_keyboard.py
cd ~/colcon_ws
colcon build --symlink-install
```



