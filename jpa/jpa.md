# JPA
- [JPA](#JPA)
- [ORM](#ORM)
- [AttributeConverter](#attributeconverter)
- [Hibernate](#Hibernate)


## Annotation
- [@EnableJpaAuditing](#@enableJpaAuditing)
- [@Where](#@where(clause-=-“deleted-=0”))
- [@DiscriminatorColumn](#@discriminatorcolumn)
- [@Inheritance](#@inheritance)
- [@MappdedSupperclass](#@mappdedsupperclass)

<hr>

### JPA

- ORM 전문가가 참여한 EJB 3.0 스펙 작업에서 기존 EJB ORM 이던 Entity Bean 을 <br>JPA 라고 바꾸고 JavaSE, JavaEE 를 위한 영속성(persistence) 관리와 ORM 을 위한 표준 기술입니다. <br>JPA 는 ORM 표준 기술로 Hibernate, OpenJPA, EclipseLink, TopLink Essentials 과 같은 <br>구현체가 있고 이에 표준 인터페이스가 바로 JPA 입니다.

### ORM

- RDB 테이블을 객체지향적으로 사용하기 위한 기술입니다. <br>RDB 은 객체지향적 (상속, 다형성, 레퍼런스, 오브젝트 등)으로 접근하기 쉽지 않습니다.<br>
때문에 ORM 을 사용해 오브젝트와 RDB 사이에 객체지향적으로 다루기 위한 기술입니다.

### Hibernate

- Boss 에서 개발한 ORM(Object Relational Mapping) 프레임워크 입니다.
	- 장점
Hibernate 는 특정 클래스에 매핑되어야 하는 데이터베이스의 테이블에 대한 관계 정의가 되어 있는 XML 파일의 메타데이터로 객체관계 매핑을 간단하게 수행시킵니다.
	- Hibernate 를 사용하면 데이터베이스가 변경되더라도 SQL 스크립트를 수정하는등의 작업을 할 필요가 없습니다. 애플리케이션에서 사용되는 데이터베이스를 변경시키고자 한다면 설정파일의 dialect 프로퍼티를 수정함으로서 쉽게 처리할 수 있습니다.
	- Hibernate 는 MySQL, Oracle, Sybase, Derby, PostgreSQL 를 포함한 많은 데이터베이스를 지원하며 POJO 기반의 모델과도 원활하게 동작합니다.

### AttributeConverter
- JPA Entity Attribute <-> Database Column 커스텀
	- ex) Database에서 사용 가능한 요일을 1,2,3으로 표현하고 있지만 Java 프로그램 내부에서는 Enum Type으로 변경하여 <br>MONDAY,TUESDAY,WEDNESDAY로 처리하고 싶을 경우.<br>
Database -> Entity<br>
Entity -> Database<br>
	- 사용법
		- AttributeConverter를 implements 후 
		- convertToDatabaseColumn와 convertToEntityAttribute 메소드를 Override해서 사용한다.
		- 항상 적용되는 것을 원할 경우 @Converter(autoApply = true)를 사용한다.

### @EnableJpaAuditing
- JPA를 사용하면 중복되는 부분들이 많이 발생한다. 
- 등록 시간, 수정 시간, id 등등.. 그런 부분을 Auditing Entity를 통해 중복을 제거하고 자동화 할 수 있다.

### @Where(clause = "deleted = 0")
-  "soft delete" 문제를 해결하기 위해 테이블에 삭제 여부를 추가하는 경우 특히 유용하다.

### @DiscriminatorColumn
- 상속매핑을 사용할때 부모 클래스에 선언한다. 하위 클래스를 구분하는 용도의 컬럼이다. 관례는 default = DTYPE

### @Inheritance
- 상속매핑을 사용할때 어떤 상속 전략을 사용 할 것인지 명시

### @MappdedSupperclass
- 테이블과 매핑되지 않고 자식 클래스 엔티티의 매핑정보를 상속하기 위해 사용된다.

- @MappedSupperclass로 지정한 클래스는 엔티티가 아니다 -> 즉, entityManager.find()나 JPQL 을 사용할 수 없다.

- 이 클래스만 단독으로 사용할일은 거의 없기 때문에, 방어코드 차원에서 abstract 로 선언하여 사용하는 것이 실수를 줄일 수 있다.


참조 : https://pkgonan.github.io/2018/03/Spring-Custom-AttributeConverter<br>
출처: https://feco.tistory.com/13 [wmJun]