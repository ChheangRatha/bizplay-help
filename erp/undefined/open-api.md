# OPEN API

 - bizplay에서 제공하는 API를 통해 ERP사에서 개발을 진행 합니다.

![](../../.gitbook/assets/image%20%2824%29.png)

                                                                             `{그림1} API방식`

   ① Message API 호출을 bizplay로 전송 합니다.  
   ② 데이터 조회/전송을 수행 합니다.  
   ③ 요청된 결과 값을 다시 전송 합니다.  
      ※ 고객을 식별할 수 있는 고유 키를 발급해 드립니다.  
      ※ 운영 환경은 Https 인증방식 암호화 합니다.

\[방화벽 설정\]  
 - bizplay는 OPEN API 로 연결 되어 아래와 같은 Out-Bound 방화벽 설정이 필요 합니다.  
  \(In-bound 없음\)

![](../../.gitbook/assets/image%20%2825%29.png)

                                                                         `{그림2} 방화벽 설정`

   ① bizplay는 목동 KT IDC센터에 금융 클라우드 센터로 운영 합니다.  
   ② 도착지 호출은 URL 방식으로 내부 서버에서 DNS를 찾을 수 없으면 HOSTS파일에 등록해야 합니다.  
   ③ 개발 API 전문테스트는 개발 작업 시 에만 필요 합니다.  
   ④ 이미지 링크는 ERP나 GW에서 첨부 이미지 링크가 필요할 경우 사용 합니다.

\[API 실습\]   
 - GET방식으로 외부 사이트를 이용하여 실습을 합니다.

![](../../.gitbook/assets/image%20%2861%29.png)

                                                                            `{그림3} API URL`

 ▶ 개발 전문을 테스트 페이지에서 확인 합니다.  
   ① [http://webankdev.appplay.co.kr/api\_test.jsp](http://webankdev.appplay.co.kr/api_test.jsp) 온라인에서 열고  
   ② 서비스 코드 목록을 ‘카드영수증 처리내역 조회\(0411\) 선택 쿼리전송 &gt; 팝업\(확인\) &gt; 잠시 대기  
       &gt; 결과 보임  
   ③ 결과 확인 [http://jsonviewer.stack.hu/](http://jsonviewer.stack.hu/) 에 접속 ②번 결과 전체 복사  
   ④ 결과 확인 페이지에 붙여넣기&gt; Format tab으로 이동

