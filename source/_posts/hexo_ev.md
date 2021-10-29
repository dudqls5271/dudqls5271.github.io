---
title: 전자정부 프레임워크 CRUD 자동 생성 기능
tags: [전자정부표준프레임워크, CRUD]
---

얼마전에 전자정부표준프레임워크 강의을 듣고온 회사 사람이 알려준 것 이다.
이 말을 듣고서 한번 프로젝트에 적용해봤는데 진짜 지금까지 했던 것들이 한번에 만들어지고 지금까지 프로젝트 찾아가면서 만들었던 시간이 아까울 정도이다.

하지만 가만히 생각하보면 이런식으로 계속 CURD을 난발 하다가는 나의 실력이 늘지 않을거 같은 느낌이 들어 요즘은 급한 작업이 아닌이상 사용하지 않는 추세이다.

우선 이클립스를 실행 시키면 우측 위에 화면처럼 eGov가 있는지 확인해준다.
만약 없다면

<p style="color:red">window -> perpective -> open Perpective -> othe</p> 에서 eGovFrame을 추가해준다.

그러면 추가가 된것을 볼 수 있을 것이다.
이제 다음과 같이 설정을 해준다.
![화면 캡처 2021-10-04 180721](https://user-images.githubusercontent.com/49426352/135825158-2a2acd49-0351-401c-8ab2-9340b3e8b59d.png)

그 다음으로 Data Source Explorer 탭으로 이동한다.
![화면 캡처 2021-10-04 181504](https://user-images.githubusercontent.com/49426352/135826709-3ca70678-0f32-40bd-9bb2-432e8c478655.png)
New을 통해서 새로 만들어준다.
![화면 캡처 2021-10-04 181603](https://user-images.githubusercontent.com/49426352/135826715-9d6831d6-9dc0-4395-a973-dba2ded14938.png)
여기서는 DB을 골라준후
![화면 캡처 2021-10-04 181629](https://user-images.githubusercontent.com/49426352/135826721-4d1583f0-13db-4a14-9496-c32b8ff4474b.png)
드라이버가 없으면 추가을 해주고 맞는 드라이버를 선택해준다.
![화면 캡처 2021-10-04 181644](https://user-images.githubusercontent.com/49426352/135826722-b8ab79a5-c14d-4b31-91d2-41fc618724fc.png)
jar List를 클릭해 주고 Add JAR/ZIP을 클릭해 준다.
![화면 캡처 2021-10-04 181747](https://user-images.githubusercontent.com/49426352/135826725-f2e0a923-a124-4f6f-a05a-fe43cbe4609c.png)
그러면 다음과 같이 선택해준 DB가 추가가 된것을 볼 수있을 것이다.

그 다음에 CRUD을 클릭후 아까 본인이 선택해준 DB을 선택후 어떠한 Table에 해한 CRUD을 만들어 줄지 선택을 해준다.
![화면 캡처 2021-10-04 181944](https://user-images.githubusercontent.com/49426352/135826741-d39d68ed-f2af-40a0-98af-dbec886b5e22.png)
![화면 캡처 2021-10-04 182003](https://user-images.githubusercontent.com/49426352/135826744-bb4a79b0-4141-43aa-9ad5-edb4932e5023.png)
그 전에 각각의 DAO, service 등은 미리 만들어 줘야 한다.
![화면 캡처 2021-10-04 181841](https://user-images.githubusercontent.com/49426352/135826726-195631b6-d3cf-4d68-be01-ba68b999c850.png)
그 다음에 작성자, 작성일 등등을 입력해주면 된다.
![화면 캡처 2021-10-04 182039](https://user-images.githubusercontent.com/49426352/135826746-76cc24f8-15b9-4304-ad9e-87d355d54de3.png)
확인버튼을 누르면 다음과 같이 만들어지는 모습을 볼 수 있을 것이다.
![화면 캡처 2021-10-04 182101](https://user-images.githubusercontent.com/49426352/135826751-02aec8f3-d230-4727-a9a2-b257b4fd08bc.png)
