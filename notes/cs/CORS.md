## CORS에러
CORS란 Cross-Origin Resource Sharing 의 약자로 교차출처 리소스 공유라는 뜻이다.   
CORS에러는 다른 출처 서버에 있는 리소스와 상호작용하여 생기는 오류이다.   
간단하게 여러개의 출처의 리소스가 동일한 Protocol + Host + Port 를 갖지 않아서 생기는 오류이다.   
이 CORS를 해결하기 위해서는    
1. 클라이언트와 서버 사이의 중계해주는 역할을 하는 프록시 서버를 구축하기
2. 서버에서 Access-Control-Allow-Origin 헤더 세팅하기   
등등이 존재한다.
