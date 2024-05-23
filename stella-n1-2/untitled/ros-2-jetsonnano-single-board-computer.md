# ROS 2 - Odroid N2+(Single Board Computer) 설정

* [ ] Single Board Computer 모델 확인하기

<!---->

* STELLA N1 – Odroid N2+ 버전에는 기본적으로  <mark style="color:red;">**Ubuntu 18.04 LTS(ROS1)가 탑재된 SD 카드가 제공됩니다.**</mark>&#x20;
* ROS 2가 필요하신 경우 하기의 링크에서 <mark style="color:red;">**.img 형식 이미지 파일을 설치합니다.**</mark>&#x20;
* 기본 탑재된 Ubuntu 20.04 LTS의 초기 비밀번호는 odroid 입니다.  &#x20;
* &#x20;<mark style="color:blue;">**하기의 링크 .img 형식 이미지 파일을 사용하시는 경우 SSH를 이용하여 원격 접속 확인만 진행하시면 됩니다.**</mark>&#x20;
* 하기 주소에서 stella\_ubuntu\_mate\_20.04\_odroid\_n2\_ros2.img 파일 다운 받으시면 됩니다.

{% tabs %}
{% tab title="사이트" %}
[http://naver.me/FPBtgJ8l](http://naver.me/FPBtgJ8l)
{% endtab %}
{% endtabs %}

* 저희가 제공하는 .img 형식 이미지 파일이 아닌 사용자께서 직접 설치를 하실 경우 하기의 과정을 참고하여 설치합니다.
* 하기의 과정을 참고하여 설치하시는 경우 발생하는 문제에 대해 대응 어려운 점 양해 부탁 드립니다.

<!---->

* [ ] SD카드에 Ubuntu 20.04 LTS 설치

<!---->

* STELLA 내 Odroid N2+에 Ubuntu 20.04를 설치합니다. 설치 방법은 하기의 링크를 참고하여 설치합니다.

{% tabs %}
{% tab title="사이트" %}
[https://dn.odroid.com/S922X/ODROID-N2/Ubuntu/](https://dn.odroid.com/S922X/ODROID-N2/Ubuntu/)
{% endtab %}
{% endtabs %}

* [ ] Ubuntu 20.04 LTS 내 ROS2 설치

<!---->

* Ubuntu 20.04 update & upgrade

```
sudo apt update && sudo apt upgrade
```

![](../../.gitbook/assets/ros2\_1.png)

* 다음 명령어를 이용하여 Ubuntu 20.04 내 ROS2를 설치합니다.

```
wget https://raw.githubusercontent.com/ntrexlab/ROS_INSTALL_SCRIPT/main/install_ros2_foxy_n2.sh&& chmod 755 ./install_ros2_foxy_n2.sh && bash ./install_ros2_foxy_n2.sh
```

![](../../.gitbook/assets/ros2\_2.png)

![](../../.gitbook/assets/ros2\_3.png)

* [ ] STELLA N1 패키지 설치

<!---->

* STELLA N1 관련 패키지 설치합니다.

```
sudo apt-get install ros-foxy-tf2 ros-foxy-joint-state-publisher
```

![](../../.gitbook/assets/ros2\_4.png)

* [ ] STELLA N1 라이브러리 설치

<!---->

* STELLA N1 라이브러리 다운로드 및 컴파일을 진행합니다.

```
cd ~/colcon_ws/src/
git clone https://github.com/ntrexlab/STELLA_ODRIOD_N2_ROS2.git
cd ~/colcon_ws/src/STELLA_ODRIOD_N2_ROS2/stella_teleop_bluetooth/stella_teleop_bluetooth/
chmod +x stella_teleop_bluetooth.py
```



* [ ] 패키지 컴파일

<!---->

* <mark style="color:purple;">**새로 터미널  실행  후**</mark>  패키지 컴파일을 진행합니다.

```
cd ~/colcon_ws
colcon build --symlink-install
```

![](../../.gitbook/assets/ROS2\_6.png)

* [ ] Serial 통신 설치

<!---->

* 센서 데이터 수집 및 모터드라이버 Command 입출력을 위한 Serial 통신 설정합니다.
* 하기의 명령어를 입력하여 USB 포트 설정합니다.

```
cd ~/colcon_ws/src/STELLA_ODROID_N2_ROS2/stella_bringup
sh create_udev_rules.sh
ls -la /dev/ 
```

![](../../.gitbook/assets/ROS2\_7.png)

* Device 목록에 YDLIDAR, AHRS, MW, BT 항목이 생성됨을 확인합니다.

<!---->

* [ ] NTP(Network Time Protocol) 서버를 이용한 시간 설정

```
sudo apt-get install ntpdate
sudo ntpdate ntp.ubuntu.com
```

* [ ] SSH를 이용하여 원격 접속 확인

```
(원격 PC에서)$ ssh odroid@[odroid의 ip주소]
```

