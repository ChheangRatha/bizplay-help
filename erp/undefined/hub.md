# HUB

\[개요\]  
 - bizplay 클라우드와 고객사 시스템\(ERP  또는 그룹웨어\)에 실시간 전문 중계가 필요한 경우  
  고객사에 설치 운영하는 프리미엄 에이전트 모듈입니다.

![](../../.gitbook/assets/image%20%2817%29.png)

                                                                                `{그림1} 구성도` 

 - 고객사가 설치 서버를 제공 하여야 합니다.   
 - OS 및 JDK 7 설치가 필요 합니다.  
 - 설치/테스트/관리를 위한 원격서비스 접속을 허용 하여야 합니다.  
 - 요청하는 방화벽을 허용 하여야 합니다.   
 - ERP/그룹웨어에 수정 및 필요한 조치는 고객사가 진행 하여야 합니다.

\[고객 준비\]  
 1. OS설치 : JDK 7 구동 가능한 Linux\(추천\) 또는 Windows. 아래 링크 참고.  
                \([http://www.oracle.com/technetwork/java/javase/config-417990.html](http://www.oracle.com/technetwork/java/javase/config-417990.html) \)  
 2. 네트워크 설정 : IP설정, 방화벽 오픈  
 3. 정보제공 : SSH 접속 계정, SAP 계정  
                      \# 개발/운영 순차적 제공도 가능  
 4. 원격접속 허용 : Linux의 경우 SSH, Windows의 경우 Terminal \(방화벽 오픈 필요\)

\[bizplay 작업\]  
 1. 미들웨어 설치 : Jetty / PostgreSQL / PgAdmin 설치  
 2. 쿠콘 Hub 프로그램 : 프로그램 설치 / 설정  
 3. 접속 테스트 : Admin 페이지  
 4. 연동 테스트 : Proxy 서비스, Agent 서비스, 모니터링 서비스 등

\[방화벽 설정\]

![](../../.gitbook/assets/image%20%2819%29.png)

![](../../.gitbook/assets/image%20%289%29.png)

                                                                      `{그림2} 방화벽 설정`                   

   ① 비즈플레이는 목동 KT IDC센터에 금융 클라우드 센터로 운영 합니다.  
   ② 도착지 호출은 URL 방식으로 내부 서버에서 DNS를 찾을 수 없으면 HOSTS파일에 등록해야 합니다.  
   ③ 이미지 링크는 ERP나 그룹웨어에서 첨부 이미지 링크가 필요할 경우 사용 합니다.  
   ④ 당사는 개발연구소를 해외법인\(캄보디아\)에서 운영 중입니다.\(원격지원은 반드시 책임자가 진행   
       합니다.\)  
   ⑤ 어드민관리는 정상 작동 로그, 오류분석용도 관리 페이지에 접속을 위한 용도 입니다.

\[HUB 설치 사양\]   
 - H/W, O/S 설치 사양 입니다.

![](../../.gitbook/assets/image%20%2848%29.png)

