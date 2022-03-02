# ROS 2 - STELLA UI 실행 - SLAM

* ROS 경우 <mark style="color:red;">**네트워크를 통한 통신을**</mark> 기반으로 구현되어 있기 때문에 <mark style="color:red;">**원격 PC 와 SBC가 동일 Wifi 네트워크 망에 연결 되어 있으며 인터넷도 정상 작동하는지 확인 후 진행합니다.**</mark>    &#x20;



* UI 상의 SLAM 버튼을 이용하여 SLAM 기능을 이용할 수 있습니다.
* SLAM 버튼을 클릭하면, 하기의 그림과 같이 RVIZ창이 열리며 SLAM 기능이 실행됩니다.
* Teleoperation 기능을 동시에 이용하여, 로봇을 이동시키며 지도를 작성할 수 있습니다.
* 원하는 만큼 지도를 작성했을 경우, Save Map 버튼을 이용하여 원하는 경로에 저장할  수 있습니다. 파일은 지정된 경로에 map.pgm , map.yaml로 저장됩니다.
* SLAM 버튼을 다시 클릭하여 SLAM 기능을 종료할 수 있습니다.

![](<../../.gitbook/assets/Screenshot from 2021-10-29 14-33-30.png>)

&#x20;

