# Annotation
- Spring
	- [@Configuration](#@Configuration)
- Jpa
	- [@EnableJpaAuditing](#@EnableJpaAuditing)

## @Configuration
- 스프링의 @Configuration 어노테이션은 어노테이션기반 환경구성을 돕는다. 
- 이 어노테이션을 구현함으로써 클래스가 하나 이상의 @Bean 메소드를 제공하고 스프링 컨테이가 Bean정의를 생성하고 런타임시 그 Bean들이 요청들을 처리할 것을 선언하게 된다. 


## @EnableJpaAuditing
- JPA를 사용하면 중복되는 부분들이 많이 발생한다. 
- 등록 시간, 수정 시간, id 등등.. 그런 부분을 Auditing Entity를 통해 중복을 제거하고 자동화 할 수 있다.