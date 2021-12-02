---
title: 서버셋팅 - CentOS7설치
tags: [서버, server, CentOS7, Linux]
---

오늘은 저번에 올렸던 <b>"서버셋팅 -VMware설치"</b>에 이어서 CentOS7을 설치 해볼 것이다.
저번 포스팅이기 때문에 저번 포스팅을 [여기!](https://dudqls5271.github.io/2021/11/29/server01/)에서 읽고 이 포스팅을 보는 것을 추천한다.

일단 CentOS을 설치 하기 전에 CentOS가 뭔지 알아야 할 것 아닌가?

> CentOS는 CentOS 프로젝트에서 레드햇 제휴로 개발한 컴퓨터 운영 체제이다. 
업스트림 소스인 레드햇 엔터프라이즈 리눅스와 완벽하게 호환되는 무료 기업용 컴퓨팅 플랫폼을 제공할 목적으로 만들어진 리눅스계 운영 체제 가운데 하나다.
출처 - 위키백과

<!--more-->

일단 저번 포스팅에서 VMware을 이용하서 공간을 나눠줬다면 이번에는 운영체제를 설치 할 순서 인것이다.

저번 포스팅에서 설정해준 VMware을 켜주는 것 까지 했는데, 상세화면을 클릭하면 아래와 같은 화면을 볼 수 있다.
여기서 인스톨을 선택하여 실행해준다.
![image](https://user-images.githubusercontent.com/49426352/144038830-e2404df8-9e0b-40c8-8eb2-52c697201d93.png)

인스톨을 선택해서 들어가면 다음과 같은 화면이 나오는데
여기서 언어는 한국어를 선택해주면 된다.
<span style="color:red;"><b>여기서 영어나 다른 언어를 선택한다면 나중에 터미널에서 귀찮게 다시 한글 셋팅을 해주어야 한다.</b></span>
![image](https://user-images.githubusercontent.com/49426352/144038849-fb3dfe48-2d57-477d-bdac-f3e491d3cbaf.png)

이제 설치 할 옵션을을 정해줘야하는데 이글에서는 디스크 / 소프트웨어 / 네트워크를 셋팅 해줄 것이다.
아래 화면에 나오는 것처럼 <span style="color:red;"><b>설치대상</b></span>을 클릭을 해준다.
![image](https://user-images.githubusercontent.com/49426352/144038881-7208eb79-7cf8-4742-8b2b-89eefa68d2e9.png)

로컬 표준 디스크 - 여기서는 저번글에서 만들어 줬던 백업용 디스크가 같이 나오게 되는데 이것을 <span style="color:red;"><b>2개다</b></span> 클릭해준다.
기타 저장소 옵션 - 여기서 보면 <span style="color:red;"><b>파티션을 자동으로 설정 합니다</b></span>에 체크가 되어 있을 것인데 이것을 <span style="color:red;"><b>파티션을 설정합니다.</b></span>로 변경해준다.
다음과 같은 설정을 해주었다면 상단에 있는 완료 버튼을 눌러준다.
![image](https://user-images.githubusercontent.com/49426352/144038983-184215a2-6e14-4c99-9ce5-2d13ca0b531d.png)

완료 버튼을 누르면 다음과 같이 파티션을 나누는 설정으로 가게 된다. 여기서 밑에 보이는 + 버튼을 통해 다음과 같은 파티션을 만들어 준다.
![image](https://user-images.githubusercontent.com/49426352/144039022-49a67c09-6112-4a52-aec7-07595c691bc4.png) ![image](https://user-images.githubusercontent.com/49426352/144039037-63c90d94-48b0-4cfd-a579-958f943b8b89.png)


다음과 같은 방식으로 만드어 준다. 여기서 보면 아래와 같이 및 기타 1을 보게 될 수 있는데, 이것을 처음에는 백업용 디스크를 잡아줘서 그런 것이다.
여기서 주위 해야 할 점은 장치에 VMware Virtual disk (sda), VMware Virtual disk (sdd)이 같은 것 처럼 보이지만 다른 2가지가 있다.
이것을 잘 구분 하여 파티션을 나줘 주길 바란다.
![image](https://user-images.githubusercontent.com/49426352/144039044-a7c5ea41-5e34-4934-8298-c5852cd8bc0d.png)

아래을 참고하여 나머지 파티션들도 만들어 준다. 사진 옆에 간단한 표를 넣어 주겠다.
![image](https://user-images.githubusercontent.com/49426352/144039071-af86929b-ace4-4ba8-bae9-e34dd7ad3183.png)
아래 표에서 /는 남은 용량 전부를 넣어주면 된다.

|마운트 지점|용량|장치|파일시스템|
|-----------|----|---|----|
|/boot|500M|sda|ext4|
|/backup|50G|sdb|ext4|
|/swap|2G|sda|ext4|
|/home|30G|sda|ext4|
|/|나머지 용량|sda|ext4|

모든 파티션을 만들어주고 완료 버튼을 누르면 다음과 같은 화면이 나오게 된다. 여기서 변경 사항 적용을 눌러주면 된다.
![image](https://user-images.githubusercontent.com/49426352/144039085-3ca252ef-7b50-46a0-96b1-1de5b04e1e59.png)

다음은 소프트웨어 선택을 눌러 작업을 진행 해줄 것이다.
![image](https://user-images.githubusercontent.com/49426352/144039094-243890ba-625a-4341-82c2-ae886e29d58f.png)

클릭을 하면 다음과 같은 화면들이 나오게 되는데
여기서 <span style="color:red;"><b>기본환경-> 기본 웹 서버</b></span>을 선택해주고 추가 옵션은 선택하지 않는다.
![image](https://user-images.githubusercontent.com/49426352/144039103-3cf122db-7737-4a57-96a1-cfa71074a7e9.png)

다음은 네트워크 및 호스팅명을 선택해서 들어가준다.
![image](https://user-images.githubusercontent.com/49426352/144039116-330523c5-2181-40c0-8383-eac395092308.png)

여기서 이더넷 부분이 꺼져있을 것인데. 이것을 켬으로 변경해주면 유동 ip로 셋팅이 된다.
![image](https://user-images.githubusercontent.com/49426352/144039125-8230065a-eb40-45f6-bf8d-0a26d59675e1.png)

위에서 했던 모든 설정을 끝내면 설치 시작 이라는 버튼이 활성화가 될 것인데, 나는 스크린샷을 찍지 않아서 기존에 있던 것을 사용해서 아래와 같이 나오는 것이다.
![image](https://user-images.githubusercontent.com/49426352/144039141-bfb747f7-ae07-48f1-9eab-878649b40566.png)

여기서 부터는 너무 쉬워서 따로 캡처를 하지 않았다. 여기서 ROOT암호와 사용자 생성을 해주면 끝난다.

> <span style="color:red;"><b>주위!!
ROOT암호와 사용자 생성은 무조건 메모장이나 해당프로젝트 README 파일에 꼭 저장 해줘야 한다.</b></span>

설치가 완료 되었으면 재부팅 버튼을 눌러서 재부팅 후 로그인해준다.
![image](https://user-images.githubusercontent.com/49426352/144039150-3be67fbe-74a4-4033-aa47-3845dcf076c1.png)

재부팅을 해주면 다음과 같이 로그인을 하라는 창이 나오는데 아까 만들어 줬던 ROOT 이름과 암호로 로그인 해주면 된다.
![image](https://user-images.githubusercontent.com/49426352/144039171-69d55c6c-f84b-4ee2-b141-496862070c0e.png)

로그인을 해주면 다음과 같은 화면이 나오게 되는데
여기서 yum update을 통해서 업데이트를 받아주면 된다.
![image](https://user-images.githubusercontent.com/49426352/144039189-ee81af6d-1876-47ef-a332-16ebef56a85a.png)

업데이트 중간에 다음과 같은화면이 나올 것인데 당황 하지말고 Y을 입력 해주고 엔터를 누르면 된다.
![image](https://user-images.githubusercontent.com/49426352/144039194-bd8317c4-6105-4e2d-9f3d-8d72cede1d4f.png)

Complete!가 뜨면 완료가 된 것이다. 
![image](https://user-images.githubusercontent.com/49426352/144039198-78f339cb-2372-47c1-87ca-ecbdbd0b9a27.png)

이상으로 CentOS7설치를 마친다.