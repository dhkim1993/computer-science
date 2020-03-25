# WEB
- [REST(REpresentational State Transfer)](#rest(representational-state-transfer))
	- [RestTemplate](#RestTemplate)
- [Jackson](#jackson)
<hr>

- REST(REpresentational State Transfer)
	- REST란, "웹에 존재하는 모든 자원(이미지, 동영상, DB 자원)에 고유한 URI를 부여해 활용"하는 것으로, <br>자원을 정의하고 자원에 대한 주소를 지정하는 방법론을 의미한다고 한다.
	- 동기
	- 비동기
	- endpoint
		- URI 별 HTTP 메소드로 구현된 항목을 Endpoint라고 합니다

- RestTemplate
	- 스프링에서 제공하는 http 통신에 유용하게 쓸 수 있는 템플릿이며, HTTP 서버와의 통신을 단순화하고 RESTful 원칙을 지킨다. <br>jdbcTemplate 처럼 RestTemplate 도 기계적이고 반복적인 코드들을 깔끔하게 정리해준다.
	- REST API 호출이후 응답을 받을 때까지 기다리는 동기방식이다
	- 스프링에서 제공하는 다른 여러 *Template 클래스 (ex. JdbcTemplate, RedisTemplate)와 동일한 원칙에 따라 설계되어 단순한 방식의 호출로 복잡한 작업을 쉽게 하도록 제공
	- RestTemplate 클래스는 REST 서비스를 호출하도록 설계되어 HTTP 프로토콜의 메서드 (ex. GET, POST, DELETE, PUT)에 맞게 여러 메서드를 제공합니다. 

- Jackson
	- jackson은 자바진영 json 라이브러리로 잘 알려져 있지만 json 뿐만 아니라 XML, YAML, CSV 등 다양한 형식의 데이타를 지원하는 data-processing 툴이다.

	- 스트림 방식이므로 속도가 빠르며 유연하며 다양한 third party 데이터 타입을 지원하며 <br>annotation 방식으로 메타 데이타를 기술할 수 있으므로 <br>JSON 의 약점중 하나인 문서화와 데이타 validation 문제를 해결할 수 있다.



출처: https://sjh836.tistory.com/141 [빨간색코딩]
