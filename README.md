# IV_SWAG_Web
**수액 모니터링 딥러닝 결과 반영 및 원격 제어를 위한 웹페이지 구현**  
<br/>

간호 스테이션을 기반으로 하는 웹페이지를 구현하여 아래의 기능을 웹페이지에서 확인하거나 제어할 수 있도록 하였습니다.
<br/><br/>
  
1. 간호 스테이션 기반 등록된 환자 선택 및 환자 정보 확인
2. 수액 방울 카운팅을 위한 딥러닝 결과 영상을 실시간 모니터링
3. 수액 방울 카운팅 결과를 바탕으로 하는 수액 주입량 실시간 모니터링
4. 원하는 수액 주입량 입력을 통한 원격 제어
5. 수액 역류 여부 확인
<br/><br/>
  
**[ 간호 스테이션(EMR) 기반 웹페이지 기본 화면 ]** <br/><br/>

![웹페이지](https://github.com/younji524/IV_SWAG_Web/assets/76142194/0588719f-2331-44b8-b761-fa7e13c04582) <br/>

<br/><br/>
**[ 딥러닝 결과 반영 ]** <br/><br/>
[ Infusion Volume ] <br/>

- 현재 주입량 확인 가능
- 설정한 주입 속도에 따라 현재까지의 예상 주입량 확인 가능

[ Flow Rate ] <br/>

- 라즈베리파이로부터 영상 획득
- 딥러닝 객체인식을 기반으로 수액 물방울 카운팅
- 소켓 통신을 통해 MariaDB로 카운팅 결과 전송
-  웹페이지에 현재 주입량을 계산하여 표시

<br/>

![웹페이지_측정부](https://github.com/younji524/IV_SWAG_Web/assets/76142194/75c27cd2-f910-4c33-ab41-640039cd234d)

<br/><br/>
**[ 수액 주입량 원격 제어 ]**  <br/><br/>
[ Flow Rate ] <br/>

- 원하는 주입 속도를 입력
- 입력된 값을 HeidiSQL 로 전송
- 라즈베리파이에서 값을 읽어 아두이노로 보내 모터 제어
<br/>

![웹페이지_조절부](https://github.com/younji524/IV_SWAG_Web/assets/76142194/9110ab57-2079-42e9-bf9a-a70a8809465c)

<br/><br/>
**[ 수액 역류 여부 확인 ]**  <br/><br/>
[ Wrist Band ] <br/>

- 아두이노에서 혈액 역류와 밴드 착용 여부를 감지
- 라즈베리파이로 정보 전송
- HeidiSQL로 전송
- 혈액 역류 여부 표시 (역류 발생 이후 시간 표시)
- 밴드 착용 여부 표시 (밴드 미착용 이후 시간 표시)
<br/>

![웹페이지_감지부](https://github.com/younji524/IV_SWAG_Web/assets/76142194/b8659561-6fe5-462c-b9dc-87ac8e90002b)

