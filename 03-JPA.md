<!--
<details>
  <summary><b></b></summary>

  ---

  <details>
    <summary></summary>
  </details>
</details> 
-->

## JPA 기본 - JDBC, SQL Mapper, ORM, Hibernate

<details>
  <summary><b>JDBC(Java Database Connectivity)란 무엇인가요?</b></summary>

  - 자바와 데이터베이스를 연결하기 위한 Java 표준 인터페이스입니다.
  - MySQL, PostgreSQL, SQL Server 등 다양한 DB 미들웨어의 드라이버를 제공합니다.
  - Java 표준이기 때문에, JVM 위에서 운영되는 모든 애플리케이션에서 사용 가능합니다.

  ---

  <details>
    <summary>JDBC을 사용하기 위해 해야하는 동작을 말해주세요.</summary>

    1. 가장 먼저 사용할 DB Driver를 선택합니다.
    2. 드라이버를 선택 후 커넥션 객체를 통해 데이터베이스와 연결합니다.
    3. SQL 쿼리를 실행하기 위해 Statement 객체를 생성합니다.
    4. 쿼리 실행 후 ResultSet 객체를 통해 받습니다.
    5. 마지막으로 커넥션 종료 시에는 메모리 누수 방지를 위해 리소스를 명시적으로 해제해야 합니다.
       예를 들어, Statement, Connection, ResultSet을 close() 메서드로 닫아야 합니다.
  </details>

  <details>
    <summary>JDBC의 단점에 대해 설명해주세요.</summary>

    단점
      - 리소스를 명시적으로 해제해야 합니다. 예를 들어, 커넥션 종료 시, 
        Statement, Connection, ResultSet 모두 close() 메서드로 종료해야 메모리 누수가 발생하지 않습니다.
      - 간단한 SQL 실행에도 중복된 코드가 반복적으로 사용됩니다.
      - DB에 따라 일관성없는 정보를 가진 채 Checked Exception으로 처리됩니다.
      
      - CheckedException
        - RuntimeException을 상속받지 않는 클래스 (ex: IOException, SQLExceptin, InterrupedException)
        - 컴파일 시점에 컴파일러를 확인하는 예외이기 때문에, 반드시 에외 처리를 해야 한다.
      - UncheckedException
        - RuntimeException을 상속하는 클래스 (ex: NPE)
        - 런타임 시점에 확인이 가능한 예외이기 때문에, 예외 처리를 강제하지 않는다.
  </details>
  <details>
    <summary>Spring JDBC에 대해 설명해주세요.</summary>

    - Spring JDBC는 스프링 프레임워크에서 제공하는 JDBC 기반의 데이터 액세스 기술입니다. 
    - Spring JDBC는 JDBC를 보다 쉽고 효율적으로 사용할 수 있도록 추상화된 기능을 제공하는데, 
      이를 통해 개발자는 반복적이고 번거로운 JDBC 작업을 간소화하고 생산성을 향상시킬 수 있다.
  </details>
  <details>
    <summary>Spring JDBC 장단점을 설명하세요.</summary>

    장점
      1) Spring JDBC는 자동으로 데이터베이스 연결, SQL 쿼리, ResultSet을 관리하고 닫아주기 때문에 
         코드를 간소화하고 메모리 누수를 방지합니다.
      2) Spring JDBC는 CheckException을 모두 UncheckedException으로 변환해 예외 처리 코드를 단순화해줍니다.
      3) Spring JDBC는 JdbcTemplate 등과 같은 다양한 템플릿과 헬퍼 클래스를 제공해 반복적인 코드를 줄이고
         데이터베이스 작업도 효율적으로 만들어줍니다. (헬퍼 클래스 : 도움을 주는 클래스)
    단점
      1) 단, 동적 SQL 쿼리를 처리하기 어렵습니다.
      2) 또한 IF 문이나, Switch Case로 인해 코드가 길어지고 지저분해질 수 있습니다.
  </details>
  <details>
    <summary>JdbcTemplate 기능에 대해 설명하세요.</summary>

    1) SQL 실행
      - 간단한 방식으로 SQL 문을 실행할 수 있습니다. 
      - 예를 들어, execute() 메서드를 사용하여 INSERT, UPDATE, DELETE 등의 작업을 실행할 수 있습니다.
      - 예를 들어, query() 메서드를 사용하여 SELECT 문을 실행하고 결과를 반환할 수 있습니다.
    2) PreparedStatement 자동 처리
      - PreparedStatement를 사용하여 SQL 문을 실행합니다.
      - 또한 JdbcTemplate이 자동으로 PreparedStatement를 생성하고 파라미터 값을 설정하기 때문에, SQL 인젝션 공격을 방지할 수 있습니다.
    3) ResultSet 매핑
      - ResultSet을 자동으로 자바 객체로 매핑해줍니다.
      - RowMapper 인터페이스를 구현하여 ResultSet의 각 행을 객체로 변환할 수 있습니다.
    4) 트랜잭션 관리
      - 트랜잭션 경계 설정, 롤백, 커밋 등의 작업을 편리하게 처리할 수 있습니다.
      - @Transactional 어노테이션을 사용하여 메서드 레벨에서 트랜잭션을 선언할 수도 있습니다.
    5) 예외 처리 및 자원 관리
      - JDBC 작업에서 발생하는 예외를 일관되게 처리하고, 연결 및 리소스 관리를 자동으로 처리합니다.
      - 즉, 예외 발생 시, 일관된 예외 계층 구조를 사용하여 예외를 처리할 수 있고, 자원의 올바른 해제를 보장합니다.
  </details>
  <details>
    <summary>Connection Pool에 대해 설명해주세요. (답변 미작성)</summary>
  </details>
  <details>
      <summary>HikariCP에 대해 설명해주세요. (답변 미작성)</summary>
  </details>
  
  ---

</details> 

<details>
  <summary><b>SQL Mapper에 대해 설명해주세요.</b></summary>

  - 객체와 SQL의 필드를 매핑해 데이터를 객체화하는 기술입니다.
  - 이는 객체와 테이블 간 관계를 매핑하는 것이 아니라, SQL문을 직접 작성하여 쿼리 수행 결과를 어떤 객체에 매핑하는 것을 말합니다.
  - 예를 들어, JDBCTemplate 혹은 MyBatis를 의미합니다.

  ---

  <details>
    <summary>MyBatis에 대해 설명하세요.</summary>

    - MyBatis는 자바 언어를 위한 데이터 매퍼 프레임워크입니다.
    - Spring JDBC는 코드에 직접 쿼리를 작성하지만 MyBatis는 XML 파일에서 SQL 쿼리를 관리하고
      SQL 결과와 객체 인스턴스의 매핑을 수행합니다.
  </details>
  <details>
    <summary>MyBatis 장/단점을 설명하세요.</summary>

    장점
      - SQL 쿼리를 직접 작성하므로 최적화된 쿼리를 구현할 수 있습니다.
      - 복잡한 쿼리도 SQL 쿼리만 작성할 수 있다면 손쉽게 작성할 수 있습니다.
      - 엔티티에 종속받지 않고 다양한 테이블을 조합할 수 있습니다.
    단점
      - 스키마 변경 시 SQL 쿼리를 직접 수정해주어야 합니다.
      - 반복된 쿼리가 발생하여 반복 작업이 있습니다.
      - 런타임 시에 오류를 확인할 수 있습니다.
      - 쿼리를 직접 작성하기 때문에 데이터베이스에 종속된 쿼리문이 발생할 수 있습니다. 
        즉, 데이터베이스 변경 시 로직도 함께 수정해주어야 합니다.
      - SQL 중심적인 개발을 하기 때문에, 객체와 관계형 테이블 구조간 패러다임 불일치 문제가 발생합니다.
  </details>
  <details>
    <summary>패러다임 불일치 문제는 무엇이 있나요?</summary>

    - 객체에는 상속 개념이 있지만 테이블에는 상속 개념이 존재하지 않습니다.
    - 객체는 연관 관계를 참조로 표현하고 테이블은 외래키로 표현합니다.
    - 객체는 그래프 탐색이 가능해야 하지만 테이블은 불가능합니다.
    - 객체는 동등성/동일성으로 비교하지만 테이블은 Row의 ID 값을 기준으로 조회합니다.
      - 동일성(Identity) : 두 객체가 완전히 같은 경우. 즉, 두 객체의 메모리 주소값이 같습니다.
      - 동등성(Equality) : 두 객체가 같은 정보를 갖고 있는 경우. 즉, 주소값이 달라도 값만 같으면 동등하다 표현합니다.
  </details>
  <details>
    <summary>SQL 중심적인 개발의 문제점에 대해 설명하세요.</summary>

    SQL에 의존적인 개발이 되기 때문에, 비지니스 로직이 SQL에 종속적이게 됩니다.
    즉, SQL에 의존적인 상황에서 개발자들이 엔티티를 신뢰하고 사용할 수 없게 됩니다.
    예를 들어, SQL 변경 시, 자바 코드도 변경해야 하므로 유지보수도 어려워집니다.
    
    최종적으로 패러다임 불일치 문제가 발생합니다. 객체지향 프로그래밍과 관계형 데이터베이스는 서로 다른 패러다임을 가지고 있습니다. 
    이 둘의 차이를 중앙에서 해결해주지 않으면 개발자가 많은 코드를 작성해야 하며, 복잡성이 증가합니다.
  </details>  
  <details>
    <summary>현업에서는 JPA를 많이 사용하긴 하지만 아직까지 JDBCTemplate 혹은 Mybatis를 사용하는 곳이 많습니다. 그 이유가 무엇일까요?</summary>

    SQL Mapper는 개발자가 SQL을 직접 작성하기 때문에, 지루하고 반복적인 코드를 작성하긴 하지만,
    SQL 지식만 충분하다면, 세밀한 SQL 쿼리 최적화가 가능하고, 복잡한 쿼리를 짜는데 용이합니다.
    또한 Entity 기준으로 동작하는 JPA보다 조회된 데이터를 바로 DTO로 변환해 응답하기가 편리합니다.
    
    그리고 JPA는 처음엔 사용하기 쉬울지 몰라도 점차 애플리케이션이 고도화된다면 오히려 더 손이 많이 가는 경우가 많아 
    아직까지 MyBatis를 사용하는 곳이 있다고 생각합니다.
  </details>
  
  ---

</details>

<details>
  <summary><b>ORM(Object Relational Mapping)이란 무엇인가요?</b></summary>

  - 객체와 Database 테이블을 매핑하여 데이터를 객체화하는 기술입니다.
  - 즉, 객체지향 프로그래밍 언어를 사용해 데이터베이스를 관리할 수 있게 합니다.
  - 대표적으로 Hibernate가 있습니다.

  ---
  
  <details>
    <summary>JPA를 Hibernate와 함께 설명해주세요.</summary>

    - JPA는 자바 ORM 기술에 대한 표준 명세를 의미합니다.즉, ORM을 사용하기 위한 인터페이스를 모아둔 것으로 
      자바에서 관계형 데이터베이스를 어떻게 사용해야 하는 지 정의되어 있기만 하고 구현되어 있지 않습니다.
    - 이 JPA를 구현한 것이 바로 Hibernate입니다. 즉, 하이버네이트는 JPA를 구현한 ORM 프레임워크입니다.
      때문에 하이버네이트를 사용하면 SQL를 사용하지 않고 직관적인 메서드를 이용해 데이터를 조작할 수 있습니다.
      단, SQL을 사용하지 않는다고 해서 JDBC를 사용하지 않는 것은 아닙니다.
  </details>
  <details>
    <summary>Spring Data JPA란 무엇인가요?</summary>

    - Spring에서 제공하는 모듈 중 하나로 개발자가 JPA를 더 쉽고 편하게 사용할 수 있도록 도와줍니다.
    - 예를 들어 JPA를 한 단게 추상화시킨 Repository 인터페이스를 제공합니다.
  </details>
  <details>
    <summary>Spring Data JPA 장/단점을 설명하세요.</summary>

    장점
      - 1차캐시, 쓰기지연, 변경감지, 지연로딩을 제공하여 성능상 이점을 얻을 수 있습니다.
      - 코드 레벨로 관리 되므로 사용하기 용이하고 생산성이 높습니다.
      - 컴파일 타임에 오류를 확인할 수 있습니다.
      - 데이터베이스에 종속적이지 않으므로 특정 쿼리를 사용하지 않아 추상적으로 기술 구현이 가능합니다.
      - 개발 초기에는 쿼리에 대한 이해가 부족해도 코드 레벨로 어느 정도 커버가 가능합니다.
      - 객체지향적으로 데이터를 관리하기 때문에, 패러다임 불일치 문제가 해결됩니다.
      - 부족한 부분은 다양한 쿼리 빌더와 호환하여 보안할 수 있습니다.
    단점
      - JPA만 사용하여 복잡한 연산을 수행하게 되면, 로직이 복잡해지거나 불필요한 쿼리가 발생할 수 있습니다.
      - 초기에는 생산성이 높을 수 있으나 점차 사용하다 보면 N+1과 같은 성능상 이슈가 발생할 수 있습니다.
      - 고도화 될수록 성능 이슈를 해결하기 위해, 학습 곡선이 높아질 수 있습니다.
  </details>
  
  ---

</details>

## JPA 심화 - JPQL, 영속성 컨텍스트
<details>
  <summary><b>@Transactional 어노테이션은 어떤 기능을 하나요?</b></summary>

  스프링에서 트랜잭션 처리는 이 어노테이션을 많이 사용하는데, 이는 클래스 또는 메소드 레벨에 사용할 수 있으며,
  @Transactional이 포함된 메소드가 호출될 경우, 프록시 객체가 생성됩니다. 이 프록시 객체는 해당 메소드 실행 이전에 
  PlatformTransactionManager를 사용하여 트랜잭션을 시작하고 결과에 따라 Commit 또는 Rollback 합니다.

  - 선언적 트랜잭션 관리 방법을 제공하는 어노테이션으로 클래스와 메서드 레벨에서 사용이 가능합니다.
  - 예를 들어, 해당 어노테이션을 붙이면 메서드나 클래스 내의 작업들이 하나의 트랜잭션으로 묶여 데이터 일관성을 유지할 수 있습니다.
  - 이는 JDBC에서 트랜잭션 사용을 위해 사용되던 코드를 단축시켜주기 때문에 매우 편리합니다.
  - 추가적으로 Spring AOP 방식으로 동작하기 때문에, 프록시 객체로 외부에서 접근이 가능한 인터페이스를 제공해야 합니다. 즉, public 메서드여야 합니다. <br/>
    또한 다른 AOP 기능들과 충돌을 고려도 하고 기본적으로 대부분의 Checked Exception은 롤백되지 않으니 예외처리도 고려해야 합니다.

  ---

  <details>
    <summary>@Transactional 동작원리에 대해 설명해주세요.</summary>

    1. 일단 @Transactional 어노테이션은 Spring AOP를 통해 프록시 객체를 생성하여 사용됩니다.
    2. 트랜잭션 어노테이션이 붙은 메서드가 실행되면 스프링은 트랜잭션을 시작합니다.
    3. 메서드가 정상적으로 종료된다면 커밋, 예외가 발생하면 롤백 처리를 합니다.
    4. 즉, 비정상 종료되어 롤백 발생 시, 트랜잭션 작업만 데이터베이스에 반영되는 것을 방지해, 데이터 일관성을 유지합니다.
  </details>
  <details>
    <summary>@Transactional 특징을 말해보세요.</summary>

    1. 자동 롤백 : 트랜잭션 내 예외 발생 시, 스프링은 자동으로 롤백합니다.
    2. 전파 행위 지정 : 트랜잭션의 전파행위를 지정할 수 있습니다.
    3. 격리 수준 설정 : 데이터베이스의 트랜잭션 거리 수준을 설정할 수 있습니다.
    4. 읽기 전용 설정 : 트랜잭션을 읽기 전용으로 설정해, 데이터 변경이 없는 작업에 대해 성능 최적화를 할 수 있습니다.
    5. 타임아웃 설정 : 트랜잭션이 너무 오래 실행되는 것을 방지하기 위해 타임아웃을 설정할 수 있습니다.
  </details>
  <details>
    <summary>@Transactional(readonly=true)는 어떤 기능인가요?</summary>

    조회용 메서드에 붙이는 것으로 영속성 컨텍스트에 snapshot을 찍지 않고, flush 모드를 수동으로 바꿔 
    의도치 않은 변경이 일어나지 않고 메모리의 성능을 높여주는 장점이 있습니다.

    - 이는 JPA의 플러시 모드를 MANUAL로 설정합니다. 즉, 트랜잭션 내에서 강제로 flush()를 호출하지 않는 한, 
      커밋 시 영속성 컨텍스트가 자동으로 flush 되지 않으므로 조회 용으로 가져온 Entity의 예상치 못한 수정을 방지할 수 있습니다.
    - 또한, JPA는 해당 트랜잭션 내에서 조회하는 Entity는 조회 용임을 인식해 변경 감지를 위한 
      Snapshot을 따로 보관하지 않으므로 메모리가 절약되기 때문에, 성능면에서의 이점도 존재합니다.

    MANUAL 모드
      - 하이버네이트 스펙에서만 지원하는 모드
      - 모든 자동 플러시가 비활성화되고, 개발자가 명시적으로 플러시 코드를 작성해야 플러시가 동작
  </details>
  <details>
    <summary>조회용 메서드에 @Transactional 어노테이션을 안 붙여도 되지 않을까요? </summary>

    - 조회용 메서드에 대해 @Transactional 어노테이션 유무의 차이는 OSIV가 꺼져있을 때 알 수 있습니다.
    - 즉, 기본적으로 별도의 설정을 하지 않는다면 OSIV는 true로 설정되어 있어 @Transactional 어노테이션 유무의 차이를 알 수 없지만,
    - OSIV를 false로 설정한다면 영속성 컨텍스트는 트랜잭션 범위를 벗어나는 순간 Entity는 영속성 컨텍스트의 관리를 받지 않는 준영속 상태가 됩니다. 
    - 따라서 영속성 컨텍스트의 관리를 받지 않는 준영속 상태는 Lazy Loading의 동작도 불가능해져 LazyInitializationException이 발생할 수 있습니다.
    - 결론적으로 OSIV가 꺼져있는 상태에서는 @Transactional 어노테이션이 없을 때에 Lazy Loading의 동작을 수행할 수 없다는 문제점이 있으므로 
      조회용 메서드에 대해서도 @Transactional 어노테이션을 붙여주어야 한다고 생각합니다.
  </details>  
  <details>
    <summary>그렇다면, 무조건 @Transactional 어노테이션을 붙이는 것이 좋을까요?</summary>

    - @Transactional 어노테이션을 붙이게 되면 해당 영역에서는 JPA의 스냅샷 유지, flush의 필요성, DB 커넥션을 오래 물고 있는 등의 관리적인 측면이 발생합니다.
    - 따라서, 지연로딩, 레플리케이션과 같이 트랜잭션 범위 내에서 수행해야 되는 동작이 있는 경우에 대해서 적절히 @Transactional 어노테이션을 활용하는 것이 좋다고 생각합니다.
    - 만약, 무분별하게 @Transactional 어노테이션을 사용한다면, 스냅샷 유지, flush의 필요 등 관리적/메모리적 측면에서 오히려 좋지 않을 수 있고, 
      커넥션을 오래 가지고 있어 커넥션 부족 등의 문제가 발생할 수도 있을 거라 생각합니다.
  </details>
  <details>
    <summary>JPA @Transactional Propagation 전파 단계를 설명해주세요. (답변 미작성)</summary>
  </details>
  
  ---

</details>

<details>
  <summary><b>JPQL(Java Persistence Query Language)이란 무엇인가요?</b></summary>

  - JPQL은 SQL과 비슷한 문법을 가지고 있지만, JPQL은 엔티티 객체를 조회하는 객체지향 쿼리입니다.
  - 또한 JPQL은 SQL을 추상화한 것이기 때문에, 특정 데이터베이스에 의존하지 않습니다. <br/>
    즉, 데이터베이스 방언이 바뀌어도 JPQL을 수정하지 않아도 됩니다.

  ---

  <details>
    <summary>JPQL 사용 시, 영속 상태가 되는 경우는 어떤 것이 있을까요?</summary>

    JPQL의 조회 대상은 엔티티, 임베디드 타입, 값 타입 같이 다양한 종류가 있습니다.
    단, JPQL는 조회한 엔티티만 영속성 컨텍스트에서 관리합니다.
    예를 들어, 임베디드 타입을 조회하거나 특정 엔티티의 필드만 조회하면 영속성 컨텍스트에서 관리되지 않습니다.
  </details>
  <details>
    <summary>JPQL 사용 시, 기존 영속성 컨텍스트의 데이터가 갱신될까요?</summary>

    JPQL 호출 시, flush가 발생하기 때문에 갱신됩니다.

    EntityMamager의 find() 메서드와 달리 JPQL은 항상 데이터베이스 SQL을 실행하며 조회합니다.
    즉, JPQL은 영속성 컨텍스트 내에 있는 데이터를 고려하지 않고 데이터베이스를 조회합니다.
    다만, 영속성 컨텍스트에 동일한 데이터가 있다면, 데이터베이스에서 조회한 데이터는 버리고
    영속성 컨텍스트 내에 있던 데이터를 반환됩니다. 때문에, 데이터 무결성을 위해, 플러시 모드를 AUTO로 하여,
    쿼리 실행 직전에 플러시하여 데이터베이스에 반영해야 합니다. 만약 성능 최적화가 필요한 로직이라면, 
    플러시 모드를 COMMIT으로 하여, 플러시 횟수를 줄일 수도 있습니다. 단, 데이터 무결성 문제가 발생할 수 있으니 주의해야 합니다.

    - AUTO : 커밋 또는 쿼리 실행 시, 플러시
    - COMMIT : 커밋 시, 플러시
  </details>
  
  ---

</details>

<details>
  <summary><b>영속성 컨텍스트란 무엇인가요?</b></summary>

  - Server와 Database 사이에 엔티티를 저장하는 논리적인 영역이라고 할 수 있습니다.
  - 예를 들어, 엔티티 매니저로 엔티티를 저장하거나 조회하면 엔티티 매니저가 영속성 컨텍스트에 엔티티를 보관하고 관리합니다.

  ---

  <details>
    <summary>영속성 컨텍스트의 이점 5가지를 설명해주세요.</summary>

    영속성 컨텍스트 사용 시, 얻는 이점으로는 1차 캐시, 동일성 보장, 쓰기 지연, 변경 감지, 지연로딩이 있습니다.

    - 1차 캐시
      - Map 객체로 저장됩니다. 이때, key 값이 @Id 값이 되고 Value는 엔티티가 됩니다. 즉, 영속 상태의 엔티티는 식별자 값이 반드시 있어야 합니다.
      - 엔티티 조회 시, 1차 캐시에 있다면 1차 캐시에서 조회하고 없다면 Database에서 조회 후 1차 캐시에 올립니다.
      - 1차 캐시로 인해, REPEATABLE READ 격리 수준을 데이터베이스가 아닌 애플리케이션 차원에서 제공합니다.
    - 동일성(Identity, ==) 보장 
      - 동일한 트랜잭션 내에서 동일성 비교가 가능합니다.
      - 영속성 컨텍스트는 특정 엔티티를 여러번 조회해도, 1차 캐시에 있는 동일한 엔티티를 반환하기 때문에 동일성이 보장됩니다.
    - 쓰기 지연:
      - SQL을 바로 보내지 않고 쓰기 지연 SQL 저장소에서 관리되다가 Flush 발생 시, 전송합니다.
    - 변경 감지(Dirty checking): 
      - 플러시가 일어날 때, 1차 캐시에 들어있는 엔티티와 스냅샵을 비교해서 값이 다르면 쓰기 지연 저장소에 업데이트 쿼리를 저장합니다. 
        마지막으로 쓰기 지연 저장소 SQL을 데이터베이스에 전송하고 커밋이 완료됩니다.
      - 단, 변경 감지는 영속 상태의 엔티티에만 적용됩니다.
      - 스냅샷 : 값을 읽어온 최초 시점
    - 지연 로딩(Lazy Loading)
      - 엔티티가 실제 사용될 때까지 데이터베이스 조회를 지연한다.
      - 지연 로딩을 위해 실제 엔티티 대신 프록시 객체를 제공한다.
      - 단, 성능 저하의 원인이 될 수도 있습니다.
  </details>
  <details>
    <summary>엔티티 생명주기를 설명해주세요.</summary>

    - 비영속(new/transient)
      - 영속성 컨텍스트와 전혀 관계가 없는 상태
      - 즉, 순수한 객체 상태를 말한다.
    - 영속(managed)
      - 영속성 컨텍스트에 저장된 상태
      - 즉, 영속성 컨텍스트가 관리하는 엔티티를 말한다.
      - `EntityManager.persist(..);`, `EntityManager.find(..);`
    - 준영속(detached)
      - 영속성 컨텍스트에 저장됐다가 분리된 상태
      - `EntityManager.detach(..);`, `EntityManager.clear(..);`, `EntityManager.close(..);`
    - 삭제(removed)
      - 삭제된 상태.
      - 즉, 엔티티를 영속성 컨텍스트와 데이터베이스에서 삭제된 것을 말한다.
      - EntityManager.remove(..);
  </details>
  <details>
    <summary>영속성은 정말 성능 향상에 큰 도움이 되나요? (답변 미작성)</summary>
  </details>
  
  ---

</details>

<details>
  <summary><b>OSIV(Open Session In View)에 대해 설명해주세요. (답변 미작성)</b></summary>

<!--
  - 영속성 컨텍스트를 View Layer까지 유지하는 속성입니다.
  - 클라이언트의 요청 시점(Filter/Interceptor-Controller)부터 영속성 컨텍스트를 생성되어 유지됨으로써 <br/>
    View Layer에서도 Entity의 지연 로딩이 가능합니다.
  - OSIV를 켠 상태에서는 @Transactional 어노테이션의 유무와 상관없이 다음 Lazy Loading을 수행하는 코드의 동작은 <br/>
    Exception 없이 정상적으로 동작합니다.
  - OSIV는 기본적으로 true이지만, OSIV 전략은 클라이언트 요청시점부터 API 응답이 끝날 때까지 영속성 컨텍스트와 데이터베이스 커넥션을 유지하므로 <br/>
    실시간 트래픽이 중요한 애플리케이션 서비스에서 커넥션 부족으로 이어질 수 있다는 큰 단점이 있습니다.
  - OSIV가 false이고 @Transactional 를 안붙인 경우 조회는 되나 바로 준영속상태가 되어 lazyloading 시, <br/>
    LazyInitializationException 발생합니다.
-->

  ---

  <details>
    <summary>한 가지 기능을 두개의 트랜잭션으로 처리할 경우 어떻게 될까요? (답변 미작성)</summary>
  </details>
  
  ---

</details>

<details>
  <summary><b>즉시 로딩과 지연 로딩에 대해 설명해주세요.</b></summary>

  - 지연로딩
    - 실제 객체가 사용되는 시점에 쿼리가 나가는 방식입니다.
    - 예를 들어, 특정 엔티티를 불러올 때 영속성 컨텍스트에 없다면, 프록시 객체로 가져오고, <br/>
      이 프록시 객체를 실제 사용하기 전까지 미루다가 실제 사용 시점에 쿼리를 실행합니다.
    - Ex: Member.getTeam() -> 프록시 객체 / Member.getTeam().getName() -> 쿼리 발생
  - 즉시 로딩
    - 조회 시, 조인을 이용해 한 번의 쿼리로 전부 조회해옵니다.
    - 즉, 실행하여 받아오는 객체는 프록시 객체가 아닌 실제 객체가 조회됩니다.

  ---

  <details>
    <summary>N + 1 문제 무엇인지 원인과 해결방안을 함께 설명해주세요. (답변 미작성)</summary>
  </details>
  
  ---

</details>


<details>
  <summary><b>플러시란 무엇인가요?</b></summary>

  플러시는 영속성 컨텍스트의 내용을 데이터베이스에 반영하는 것을 말합니다. <br/>
  즉, 영속성 컨텍스트의 내용을 데이터베이스와 동기화하는 것입니다. 단, 영속성 컨텍스트를 비우지는 않습니다.

  - 플러시 방법
    - EntityManager.flush() : 직접 호출
    - 트랜잭션 커밋 : 자동 호출
    - JPQL 쿼리 실행 : 자동 호출
   
  ---

  <details>
    <summary>플러시 발생 시, 일어나는 일을 설명하세요.</summary>

    - 영속성 컨텍스트의 내용을 데이터베이스와 동기화하는 것이기 때문에, 플러시가 발생한다면 가장 먼저, 변경 감지가 일어납니다.
    - 그리고 변경된 것이 있다면, 데이터베이스에도 반영하기 위해 쓰기 지연 SQL 저장소에 해당 변경 쿼리를 추가합니다.
    - 마지막으로 쓰기 지연 저장소의 쿼리를 데이터베이스에 전송합니다.
  </details>
  
  ---

</details>

## Reference

- [https://www.inflearn.com/course/ORM-JPA-Basic](https://www.inflearn.com/course/ORM-JPA-Basic)
- [https://hongguri.tistory.com/](https://hongguri.tistory.com)
- [https://code-lab1.tistory.com/](https://code-lab1.tistory.com/)
- [https://jojoldu.tistory.com/](https://jojoldu.tistory.com/)
- [https://steady-coding.tistory.com/](https://steady-coding.tistory.com/)
- [https://incheol-jung.gitbook.io/docs/q-and-a/spring/](https://incheol-jung.gitbook.io/docs/q-and-a/spring/)
- [https://hungseong.tistory.com/74](https://hungseong.tistory.com/74)
