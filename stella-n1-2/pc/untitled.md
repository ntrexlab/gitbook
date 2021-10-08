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



