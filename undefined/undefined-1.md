# 모터 게인 확인 및 수정

* 자사 제품 모터드라이버는 GUI를 이용하여 간단하게 모터를 튜닝 할 수 있습니다. STELLA 중량이 크게 변경되거나 모터 제어가 비정상적인 경우 게인을 변경하셔야 합니다.



* 당사의 모터 드라이버 프로그램 다운로드

{% tabs %}
{% tab title="프로그램 다운 사이트" %}
[https://www.devicemart.co.kr/goods/view?no=1077424#goods\_file](https://www.devicemart.co.kr/goods/view?no=1077424#goods\_file)
{% endtab %}
{% endtabs %}

* [ ] 모터 게인 방법

<!---->

* 모터드라이버를 USB를 통해 PC에 연결합니다.
* Mobile\_UI를 실행 후 Scan Devices 버튼을 클릭합니다.

![](<../.gitbook/assets/md\_1 (1).png>)

* Real-time Plot 버튼을 클릭합니다.

![](../.gitbook/assets/GAIN\_1.png)

* Objects Selection 버튼을 클릭합니다.

![](../.gitbook/assets/GAIN\_2.png)

* Objects Selection Dialog를 화면과 같이 세팅해줍니다. 만약 모터 하나씩 해주고 싶은 경우는 Velocity Command와 Veloctiy 를 채널 1로 하나씩만 하고 다음에 채널 2로 하나씩 설정 후 진행하면 됩니다.

![](../.gitbook/assets/GAIN\_3.png)

* 모터 게인 튜닝이 잘 된 경우 – 속도 에러율이 높을 때 빠른 시간 내에 값을 찾아갑니다.

![](../.gitbook/assets/GAIN\_4.png)

* 모터 게인 튜닝이 이상한 경우 – 속도 에러율이 높을 때 시간 내에 빨리 찾아가지 못하고 튀는 모습을 볼 수 있습니다. 이런 경우 게인을 다시 튜닝 해야합니다.

![](../.gitbook/assets/GAIN\_5.png)
