# OPEN API

\[개요\]  
 - bizplay에서 제공하는 API를 통해 ERP사에서 개발을 진행 합니다.

![](../../.gitbook/assets/image%20%2867%29.png)

                                                                             `{그림1} API방식`

   ① Message API 호출을 bizplay로 전송 합니다.  
   ② 데이터 조회/전송을 수행 합니다.  
   ③ 요청된 결과 값을 다시 전송 합니다.  
      ※ 고객을 식별할 수 있는 고유 키를 발급해 드립니다.  
      ※ 운영 환경은 Https 인증방식 암호화 합니다.

\[방화벽 설정\]  
 - bizplay는 OPEN API 로 연결 되어 아래와 같은 Out-Bound 방화벽 설정이 필요 합니다.  
  \(In-bound 없음\)

![](../../.gitbook/assets/image%20%2871%29.png)

                                                                         `{그림2} 방화벽 설정`

   ① bizplay는 목동 KT IDC센터에 금융 클라우드 센터로 운영 합니다.  
   ② 도착지 호출은 URL 방식으로 내부 서버에서 DNS를 찾을 수 없으면 HOSTS파일에 등록해야 합니다.  
   ③ 개발 API 전문테스트는 개발 작업 시 에만 필요 합니다.  
   ④ 이미지 링크는 ERP나 GW에서 첨부 이미지 링크가 필요할 경우 사용 합니다.

\[API 실습\]   
 - GET방식으로 외부 사이트를 이용하여 실습을 합니다.

![](../../.gitbook/assets/image%20%28177%29.png)

                                                                            `{그림3} API URL`

 ▶ 개발 전문을 테스트 페이지에서 확인 합니다.  
   1. [http://webankdev.appplay.co.kr/api\_test.jsp](http://webankdev.appplay.co.kr/api_test.jsp) 열고

![](../../.gitbook/assets/image%20%2852%29.png)

                                                                       `{그림4} API TEST`

   2. ①"서비스 코드 목록"에 "카드 영수증 처리 내역 조회\(0411\)" 선택하여 ②"쿼리전송"을 클릭 합니다.  
       ③ JSON\_OUT 결과물이 나옵니다.  
   3. 결과 확인 [http://jsonviewer.stack.hu/](http://jsonviewer.stack.hu/) 에 접속하여

![](../../.gitbook/assets/image%20%2899%29.png)

                                                                     `{그림5} JSON Viewer 화면`

   4.  ③번 결과물을 ④"Text" 항목 선택 후 붙여넣기를 합니다.  
        ⑤"Format" 탭을 클릭하면 결과물이 정렬됩니다.

![](../../.gitbook/assets/image%20%2870%29.png)

                                                                     `{그림6} JSON Viewer 화면`

 5.  ⑥"viewer" 탭을 클릭하면 정렬된 결과물을 확인 할 수 있습니다.

 ▶ get 방식 API테스트  
    - URL 인코딩된 API 입력값 구하기  
      URL인코딩\(base64\) : Protocol로 사용하는 http URL에는 의미를 가진 문자가 있음 해당문자를 URL에  
     명령어로 인식하지 못하도록 암호화 하는 방법

![](../../.gitbook/assets/image%20%28112%29.png)

                                                                      `{그림7} API TEST`

   ``① "서비스코드 목록" 에서 "카드 영수증 처리 내역 조회 \(0411\) 선택합니다.  
          ② JSON\_IN 입력된 내역을 복사합니다. 

![](../../.gitbook/assets/image%20%28141%29.png)

                                                                        `{그림8} URL 인코딩`

   ``③ [http://www.convertstring.com/ko/EncodeDecode/UrlEncode ](http://www.convertstring.com/ko/EncodeDecode/UrlEncode%20) 접속하여   
             복사한 내역을 "여기에 URL 인코딩하고자하는..." 붙여 넣습니다.  
          ④ "URL 인코딩!"을 클릭합니다.  
          ⑤ "여기에 URL 인코딩 된 텍스트를 복사 : " 출력물 값을 복사합니다.

![](../../.gitbook/assets/image%20%28147%29.png)

                                                                        `{그림9} 메모장`

        ⑥ 메모장안에 "http://webankdev.appplay.co.kr/geteway.do?JSONData=" 입력합니다.  
        ⑦에 ⑤결과물을 붙여 넣습니다.

![](../../.gitbook/assets/image%20%2889%29.png)

                                                                       `{그림10} Chrome 주소란`              

        ⑧ "Chrome" 실행하여 주소란에 "{그림9} 메모장" 안에 있는 내용을 복사하여 붙여넣습니다.

![](../../.gitbook/assets/image%20%28148%29.png)

                                                                   `{그림11} URL인코딩 실행 화면`

       ⑨ URL 실행 후 결과물을 복사합니다.  
          위에 "▶ 개발 전문을 테스트 페이지에서 확인 합니다." 에서 3~5 설명되어 있는데로  
         실습을 합니다.

 ▶ 리바운드 전문  
   -  전문 통신 특성상 응답을 무한정 길게 전송이 불가능하기 때문에 일정 건별로 페이징을 반복하여   
     전문을 호출합니다.   

![](../../.gitbook/assets/image%20%28122%29.png)

                                `{그림12} NEXT_KEY 적용 화면`

   ① 쿼리전송을 하여 JSON\_OUT 결과창에 "NEXT\_KEY" 값이 있는지 확인합니다.  
       "NEXT\_KEY" 값이 있으면 다음 페이지가 존재하기 때문에 다시 요청을 하여야 합니다.  
   ② JSON\_IN 창에 "NEXT\_KEY" :" 뒤에 ①JSON\_OUT 창에  나온 "NEXT\_KEY"을 입력 후 쿼리전송을 합니다.



