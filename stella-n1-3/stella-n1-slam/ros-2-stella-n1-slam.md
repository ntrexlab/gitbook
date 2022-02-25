# ROS 2 - STELLA N1 SLAM

* 자율주행을 하기 위해 필요한 기능 중 하나인 SLAM(Simultaneous localization and mapping) 기능을 이용하고자 합니다. SLAM이란 로봇이 주변을 탐색하여 로봇의 현재 위치 및 지도를 추정할 수 있는 기술입니다. STELLA N1을 이용하여 Cartographer 알고리즘으로 구현된 SLAM 기능을 이용하고자 합니다. SLAM 기능을 사용하기 위해 하기의 과정에 따라 진행합니다.



* [ ] STELLA N1 구동 파일 실행&#x20;

<!---->

* <mark style="color:red;">**원격PC 새로운 터미널**</mark>에서 SSH로 N1 SBC에 접속합니다.

```
ex) ssh ntrex@192.168.0.xxx 입력 후 패스워드 입력
```

* <mark style="color:red;">**위 빨간 글 SSH 접속 터미널**</mark>에서 명령어를 입력합니다. &#x20;

```
ros2 launch stella_bringup robot.launch.py
```

![](../../.gitbook/assets/064.png)

* [ ] SLAM 노드 실행

<!---->

* <mark style="color:green;">**원격PC 새로운 터미널**</mark>에서 하기의 명령어를 입력합니다.

```
ros2 launch stella_cartographer cartographer.launch.py
```

![](../../.gitbook/assets/066.png)

![](../../.gitbook/assets/067.png)

* [ ] 키보드 조작을 통해 주행과 함께 주변 환경 매핑(mapping)

<!---->

* <mark style="color:orange;">**원격PC에서 새로운 터미널**</mark>에서 하기의 명령어를 입력합니다.

```
ros2 run stella_teleop teleop_keyboard
```

* [ ] 완성된 지도 저장&#x20;

<!---->

* Map\_Server를 이용하여 지도를 저장합니다. 저장된 지도는 /home// 경로에 map.pgm, map.yaml로 저장됩니다.
* <mark style="color:blue;">**SLAM 노드를 종료하지 않은 상태로 원격PC 새로운 터미널**</mark>에서 하기의 명령어를 입력합니다.

```
ros2 run nav2_map_server map_saver_cli -f ~/map
```

