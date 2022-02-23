---
description: >-
  자신의 Single Board Computer의 맞게 설치 하셔야 됩니다. Jetson Nano 옵션을 선택하셨으면 밑에 Jetson
  Nano 설정을 참고 해주시면 됩니다.
---

# ROS 2 - Raspberry Pi(Single Board Computer) 설정

* [ ] single Board Computer 모델 확인하기

<!---->

* STELLA N1 – Raspberry Pi 버전에는 <mark style="color:red;">**Raspberry Pi OS(ROS1)가 탑재된 SD카드 제공됩니다.**</mark>&#x20;
* ROS 2가 필요하신 경우 하기의 링크에서 IMG 파일을 설치합니다.     해당 SBC도 원격 PC와 동일하게 ROS 2 및 STELLA 라이브러리 설정이 필요합니다.
* STELLA N1 구매 시, 제공하는 Raspberry Pi를 사용하실 경우 기본적으로 하기와 같은 과정이 전부 작업된 <mark style="color:red;">**Raspberry Pi OS가 탑재된 SD카드 제공됩니다.**</mark>
* SD카드를 삽입하여 사용하시면 됩니다.
* OS 재 설치가 필요하신 경우 하기의 링크에서 IMG 파일을 재 설치 합니다.

{% tabs %}
{% tab title="STELLA N1 IMG" %}
[http://gofile.me/4Z3Cs/UnXF9KC9j](http://gofile.me/4Z3Cs/UnXF9KC9j)
{% endtab %}
{% endtabs %}

* 기본 탑재된 Raspberry Pi OS의 초기 비밀번호는 1 입니다.
*   저희가 제공하는 IMG 파일이 아닌 사용자께서 직접 설치를 하실 경우 하기의 과정을

    &#x20;참고하여 설치합니다.

<!---->

* [ ] Raspberry Pi OS 설치

<!---->

* STELLA 내 Raspberry Pi에 Raspberry Pi OS를 설치합니다. 설치 방법은 하기의 링크를 참고하여 설치합니다.

{% tabs %}
{% tab title="Raspberry 사이트" %}
[https://www.raspberrypi.org/documentation/computers/getting-started.html](https://www.raspberrypi.org/documentation/computers/getting-started.html)
{% endtab %}

{% tab title="Second Tab" %}

{% endtab %}
{% endtabs %}

* [ ] Raspberry Pi OS 설치 후 하기의 명령어를 통해 최신 버전으로 업데이트합니다.

```
sudo apt-get update && sudo apt-get upgrade
```

* [ ] Raspberry Pi OS 내 ROS 설치

<!---->

* 다음 명령어를 이용하여 Raspberry Pi OS 내 ROS2를 설치합니다.

```
wget https://raw.githubusercontent.com/ntrexlab/ROS_INSTALL_SCRIPT/main/install_ros2_foxy_rp4.sh && chmod 755 ./install_ros2_foxy_rp4.sh && bash ./install_ros2_foxy_rp4.sh
```

* [ ] STELLA N1 라이브러리 설치

<!---->

* STELLA N1 라이브러리 다운로드 합니다.

```
cd ~/colcon_ws/src/
git clone https://github.com/ntrexlab/STELLA_RASPBERRYPI_ROS2.git
cd ~/colcon_ws/src/STELLA_RASPBERRYPI_ROS2/stella_teleop_bluetooth/stella_teleop_bluetooth/
chmod +x stella_teleop_bluetooth.py
```

* [ ] 패키지 컴파일

<!---->

* 패키지 컴파일을 진행합니다.

```
cd ~/colcon_ws
colcon build --symlink-install
```

* [ ] Serial 통신 설치

<!---->

* 센서 데이터 수집 및 모터드라이버 Command 입출력을 위한 Serial 통신 설정합니다.
* 하기의 명령어를 입력하여 USB 포트 설정합니다.

```
cd ~/colcon_ws/src/STELLA_RASPBERRYPI_ROS2/stella_bringup
sh create_udev_rules.sh
ls -la /dev/ 
```

* Device 목록에 YDLIDAR, AHRS, MW, BT 항목이 생성됨을 확인합니다.

<!---->

* [ ] Raspberry Pi SD카드 설정

<!---->

* Raspberry Pi 내 장착되어 있는 SD카드 메모리를 전부 활용할 수 있도록 다음의 과정을 진행합니다.

```
sudo raspi-config
    -> 6 Advanced Options를 선택
    -> A1 Expand Filesystem을 선택
```

* [ ] NTP(Network Time Protocol) 서버를 이용한 시간 설정

```
sudo ntpdate ntp.ubuntu.com
```

* [ ] SSH를 이용하여 원격 접속 확인

<!---->

* Raspberry Pi에 원격으로 접속할 수 있도록 다음의 과정을 진행합니다.

```
sudo raspi-config
    -> 3  Interface Options를 선택
    -> P2 SSH를 선택하여 SSH를 Enable함
```

* 추가적으로, 비밀번호 재 설정 후 원격 PC 에서 SSH를 통해 원격 접속합니다.

```
(원격 PC에서)$ ssh pi@[Raspberry Pi의 ip주소]
```

