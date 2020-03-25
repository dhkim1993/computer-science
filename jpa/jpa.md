#JPA
- [AttributeConverter](#attributeconverter)

## Annotation
- [@EnableJpaAuditing](#@EnableJpaAuditing)
- [@Where](#where(clause-=-“deleted-=0”))
- [@DiscriminatorColumn](#@discriminatorcolumn)
- [@Inheritance](#@inheritance)
- [@MappdedSupperclass](#@MappdedSupperclass)

<hr>

###AttributeConverter
- JPA Entity Attribute <-> Database Column 커스텀
	- ex) Database에서 사용 가능한 요일을 1,2,3으로 표현하고 있지만 Java 프로그램 내부에서는 Enum Type으로 변경하여 <br>MONDAY,TUESDAY,WEDNESDAY로 처리하고 싶을 경우.<br>
Database -> Entity<br>
Entity -> Database<br>
	- 사용법
		- AttributeConverter를 implements 후 
		- convertToDatabaseColumn와 convertToEntityAttribute 메소드를 Override해서 사용한다.
		- 항상 적용되는 것을 원할 경우 @Converter(autoApply = true)를 사용한다.

###@EnableJpaAuditing
- JPA를 사용하면 중복되는 부분들이 많이 발생한다. 
- 등록 시간, 수정 시간, id 등등.. 그런 부분을 Auditing Entity를 통해 중복을 제거하고 자동화 할 수 있다.

### @Where(clause = "deleted = 0")
-  "soft delete" 문제를 해결하기 위해 테이블에 삭제 여부를 추가하는 경우 특히 유용하다.

###@DiscriminatorColumn
- 상속매핑을 사용할때 부모 클래스에 선언한다. 하위 클래스를 구분하는 용도의 컬럼이다. 관례는 default = DTYPE

###@Inheritance
- 상속매핑을 사용할때 어떤 상속 전략을 사용 할 것인지 명시

###@MappdedSupperclass
- 테이블과 매핑되지 않고 자식 클래스 엔티티의 매핑정보를 상속하기 위해 사용된다.

- @MappedSupperclass로 지정한 클래스는 엔티티가 아니다 -> 즉, entityManager.find()나 JPQL 을 사용할 수 없다.

- 이 클래스만 단독으로 사용할일은 거의 없기 때문에, 방어코드 차원에서 abstract 로 선언하여 사용하는 것이 실수를 줄일 수 있다.


참조 : https://pkgonan.github.io/2018/03/Spring-Custom-AttributeConverter<br>
출처: https://feco.tistory.com/13 [wmJun]