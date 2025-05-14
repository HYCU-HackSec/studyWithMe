# 01. HTTP 헤더에서 가지고 올 수 있는 정보들 목록
- 헤더는 클라이언트와 서버 간에 부가적인 정보(메타데이터)를 전달하는 데 사용

```
요청 헤더 (Request Headers):
host: 요청한 서버의 도메인 이름과 포트 번호 (필수)
User-Agent: 요청을 보낸 클라이언트의 정보 (예: 브라우저 종류, 운영체제)
Accept: 클라이언트가 받을 수 있는 응답 데이터의 미디어 타입 (Content-Type) 목록
Accept-Language: 클라이언트가 선호하는 언어
Accept-Encoding: 클라이언트가 받을 수 있는 콘텐츠 인코딩 방식 (예: gzip, deflate)
Referer: 현재 요청 이전에 사용자가 머물렀던 웹 페이지의 주소
Cookie: 서버가 이전에 클라이언트에게 전송했던 쿠키 데이터
Authorization: 클라이언트의 인증 정보를 담습니다. (예: Bearer token, Basic 인증 정보)
Content-Type: 요청 본문에 담긴 데이터의 미디어 타입 (방금 논의한 application/json, multipart/form-data 등)
Content-Length: 요청 본문의 크기 (바이트 단위)
Cache-Control: 캐싱 메커니즘을 제어합니다.
Connection: 클라이언트와 서버의 연결 상태 (예: keep-alive)
If-Modified-Since, If-None-Match: 캐시된 리소스의 유효성을 검사할 때 사용
```

```
응답 헤더 (Response Headers): 
Content-Type: 응답 본문에 담긴 데이터의 미디어 타입
Content-Length: 응답 본문의 크기
Status Line: 응답의 상태 코드와 설명 (예: HTTP/1.1 200 OK) - 엄밀히는 헤더는 아니지만 헤더의 시작 줄입니다.
Server: 응답을 생성한 웹 서버의 정보
Date: 응답이 생성된 날짜와 시간
Set-Cookie: 클라이언트에게 저장하도록 지시하는 쿠키 데이터
Cache-Control, Expires, Pragma: 클라이언트 캐싱 메커니즘 제어
Location: 리다이렉션될 새로운 페이지의 주소 (3xx 상태 코드와 함께 사용)
WWW-Authenticate: 클라이언트가 인증을 요구받았을 때 (401 Unauthorized) 사용해야 할 인증 방식 정보
```

# 02. HTTP 본문에서 정보를 가져오는 방법 (Content-Type의 종류)
- HTTP 본문은 실제 전송하려는 데이터 자체를 담는 공간
- 텍스트 파일, 이미지 파일, 오디오, 비디오, HTML 문서, XML 데이터, JSON 데이터 등 어떤 종류의 데이터든 본문에 담아 보낼 수 있다

## Content-Type 헤더 : 본문에 담긴 데이터가 어떤 형식으로 인코딩/구성되어 있는지
- Content-Type 헤더에 지정될 수 있는 값은 **MIME 타입(Media Type)**이라고 불리며
- 앞으로도 계속해서 추가되어 나갈 수 있다.(생겨 난다는 이야기)

```
데이터를 가져오거나 해석하기 위해 사용되는 Content-Type의 예는 다음과 같습니다.

text/plain: 순수 텍스트 데이터
text/html: HTML 문서
text/css: CSS 스타일시트
text/javascript: JavaScript 코드
application/xml: XML 데이터
application/octet-stream: 정의되지 않은 임의의 이진 데이터 (실행 파일 등)
image/jpeg, image/png, image/gif: 이미지 데이터
audio/mpeg, video/mp4: 오디오/비디오 데이터
application/pdf: PDF 문서
...등 수백, 수천 가지의 MIME 타입이 존재
```
