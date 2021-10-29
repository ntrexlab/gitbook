# ROS 2 - STELLA N1 Navigation

* 완성된 지도를 이용하여 지도 내에 원하는 목적지로 주행하는 기능을 사용합니다.



* [ ] STELLA N1 구동 파일 실행&#x20;
* [ ] SSH를 이용하여 STELLA N1 SBC로 원격 접속하여 하기의 명령어를 실행합니다.

```
 (SSH 접속 후) ros2 launch stella_bringup robot.launch.py
```



* [ ] STELLA Navigation 실행&#x20;
* [ ] 원격 PC에서 stella\_navigation2 실행합니다. 이 때, map\_file의 경로를 지정해주며 /home/ 위치에 $HOME/.yaml로 지정합니다.

```
ros2 launch stella_navigation2 navigation2.launch.py map:=$HOME/map.yaml
```

![ ](<../../.gitbook/assets/Screenshot from 2021-10-29 14-23-05.png>)

* [ ] Navigation 기능을 이용하여 목적지 이동&#x20;
* [ ] 저장된 지도와 STELLA N1의 위치가 UI와 같은 rviz 프로그램 창에서 나타납니다.
* [ ] Rviz 상단에 위치한 2D Pose Estimate 버튼을 누르고 STELLA의 실제 위치에 놓은 후, 더 정확한 위치 추정을 위해 키보드를 사용하여 주변을 이동하며 localization을 수행합니다.
* [ ] 상단에 위치한 2D Nav Goal 버튼을 누르고 목적지를 클릭하여 STELLA N1을 이동시킵니다.
