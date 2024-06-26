<!--
<details>
  <summary><b></b></summary>

  ---

  <details>
    <summary></summary>
  </details>
</details> 
-->

## 객체지향
<details>
  <summary><b>객체지향 4가지 특징에 대해 설명하세요.</b></summary>

  - 객체지향 4가지 특성 중 적용한 특성이 있나요?
  - 오버로딩과 오버라이딩 차이점에 대해 설명하세요.
  - 클래스, 객체, 인스턴스 차이에 대해 설명하세요.
  - 접근 제어자에 대해 설명하세요.
  - 추상 클래스와 인터페이스 차이점에 대해 설명하세요.
  - 본인은 어떤 기준으로 추상 클래스와 인터페이스를 사용하는지 알려주세요.
</details>
<details>
  <summary><b>SOLID 5원칙에 대해 설명하세요.</b></summary>

  - SOLID 원칙에서 가장 중요하다고 생각하는 원칙이 있나요?
  - DIP를 적용해본 경험이 있나요?
</details>
<details>
  <summary><b>객체지향, 절차지향, 함수형 프로그래밍 차이점에 대해 설명하세요.</b></summary>

  - 자바의 함수형 프로그래밍 예시를 설명하세요.
  - 일급 객체에 대해 설명하세요.
</details>

## Java Version

<details>
  <summary><b>Java 8에 대해 설명해주세요.</b></summary>

</details>
<details>
  <summary><b>Java 11에 대해 설명해주세요.</b></summary>

</details>

<details>
  <summary><b>Java 17에 대해 설명해주세요.</b></summary>

</details>

<details>
  <summary><b>Java 21에 대해 설명해주세요.</b></summary>

  - Virtual Thread에 대해 설명해주세요.
</details>

## Java 기초

<details>
  <summary><b>Primitive Type과 Reference Type의 차이점에 대해 설명하세요.</b></summary>

  - Wrapper Class에 대해 설명하세요.
  - Call By Reference와 Call By Value에 대해 설명하세요.
</details>
<details>
  <summary><b>Java의 Exception에 대해 설명해 주세요.</b></summary>

  ![image](https://github.com/HyuckJuneHong/Tech-Interview/assets/31675711/56efe881-6e81-4275-8d1b-d55b7c674c34)
  > [그림 출처](https://velog.io/@agugu95/java-exception-and-error)

  ---

  <details>
    <summary>프로그래밍의 오류 종류는 무엇이 있을까요?</summary>

    - 컴파일 에러
      - 컴파일 시 발생하는 에러입니다.
      - 컴파일 단계에서 오류 발견 시, 컴파일러가 에러 메시지를 출력해주는 에러를 말합니다.
    - 런타임 에러
      - 실행 시 발생하는 에러입니다.
      - 컴파일 문제가 없더라도, 프로그램 실행 중에 에러가 발생해 잘못된 결과를 얻거나, 
        외부적인 요인으로 프로그램이 비정상 종료되는 에러를 말합니다.
    - 논리적 에러
      - 실행은 되지만, 의도와 다르게 동작하는 에러입니다.
      - 일종의 버그라고 할 수 있습니다.
      - 실행 및 작동에 아무 문제가 없지만, 결과가 예상과 다른 에러입니다.
  </details>
  <details>
    <summary>Error와 Exception의 차이점에 대해 설명해주세요.</summary>

    자바에서의 오류는 프로그램 실행 중 어떤 원인에 의해 오작동 혹은 비정상 종료되는 경우를 프로그램 오류라고 합니다.
    자바에서 이 오류가 Error(에러)와 Exception(예외)로 나뉘는데, 메모리 부족같은 복구할 수 없는 오류를 에러라고 하고
    NPE와 같이, 예측해서 상황에 맞게 처리할 수 있는 오류를 예외라고 합니다.
    
    - 에러(Error)
      - 시스템이 종료되어야할 수준과 같이 수습할 수 없는 심각한 문제입니다.
      - 이는 개발자가 미리 예측하여 방지할 수 없습니다.
      - Ex) StackOverflowError : 호출의 깊이가 깊어지거나, 재귀가 지속되어 stack overflow 발생 시, 던지는 에러입니다.
      - Ex) OutOfMemoryError : JVM이 할당한 메모리 부족으로 더 이상 객체를 할당할 수 없을 때 던지는 에러입니다.
                               이는, GC에 의해 추가적인 메모리가 확보되지 못하는 상황이기도 합니다.
    - 예외(Exception)
      - 이는 개발자가 미리 예측해서 상황에 맞는 예외처리를 할 수 있습니다.
      - 예외는 오류와 다르게 개발자가 임의로 예외를 던질 수 있습니다.
      - 예외는 RuntimeException과 Exception으로 나뉩니다.
      - Ex) NullPointerException : 객체가 필요한 경우에 null을 사용하려고 시도한 경우 던지는 예외입니다.
      - Ex) IllegalArgumentException : 메서드가 허가되지 않거나 부적절한 Argument를 받았을 때, 던지는 예외입니다.
    
    - 공통점
      - 오류나 예외 모두 Object 클래스를 상속 받는 Throwable 클래스를 상속 받습니다.
      - Throwable 객체는 오류나 예외에 대한 메시지를 담고, 예외가 연결될 때 해당 예외의 정보를 기록합니다.
        이를 위해, Throwable 클래스에는 getMessage()와 printStackTrace() 함수가 구현되어 있습니다.
  </details>
  <details>
    <summary>CheckedException, UncheckedException 의 차이에 대해 설명해 주세요.</summary>

    - CheckedException (컴파일 에외 클래스들)
      - 예외 처리하지 않을 시, 컴파일되지 않기 때문에, 예외 처리가 필수입니다.
      - JVM 외부와 통신(네트워크, 파일 시스템 등) 시, 주로 사용됩니다.
      - RuntimeException을 상속받지 않는 모든 예외를 말합니다.
      - Ex) IOExceptiom, SQLException 등
    - UncheckedException (런타임 예외 클래스들)
      - 예외 처리하지 않아도, 컴파일이 가능합니다.
      - RuntimeException을 상속받는 모든 예외입니다.
      - Ex) NPE, IndexOutOfBoundException 등
  </details>
  <details>
    <summary>예외 처리(Exception Handling)를 하는 방법에 대해 설명해 주세요.</summary>

    - `try-catch`문으로 감싸서 복구 및 전환하거나, Throws로 던져서 회피하여 처리할 수 있습니다.
      1. 예외 복구 전략 : try-catch를 사용해 예외가 발생해도 애플리케이션이 정상적으로 동작할 수 있도록 처리하는 전략
      2. 예외 회피 전략 : 예외 발생 시, throws를 활용해 호출된 부분으로 예외를 던져서 회피하는 전략
      3. 예외 전환 전략 : Checked Exception을 명확하게 어떤 문제가 발생하는 지 Unchecked Exception으로 전환하는 전략
  </details>
  <details>
    <summary>try-with-resource에 대해 설명하세요.</summary>

    try-with-resource는 try 블록이 끝날 때, 자동으로 자원을 해제해주는 기능입니다.

    - 보통 DB, Network, File 등과 같은 자원을 사용 후 자원을 해제해야 하는데, 실수 및 에러로 인해, 자원이 해제되지 않을 수 있습니다.
    - 이 `try-with-resource`문을 이용하면, try 블록이 끝나자마자 자동으로 할당된 자원을 해제해 줍니다.
    - 단, `try-with-resource`을 사용하려면, AutoCloseable 인터페이스를 구현하고 있어야 합니다.

    - 특징
      - 자원 반납에 의해 코드가 복잡해지던 문제를 해결
      - 실수 및 에러로 인해 자원을 반납하지 못하던 문제 해결
      - 에러 스택 트레이스가 누락되던 문제 해결
      - Java 7에 도입
  </details>
  <details>
    <summary>AutoCloseable, Closeable 차이점에 대해 설명하세요.</summary>

    이 둘은 거의 똑같은데, Closeable은 IOException으로 범위가 더 좁습니다. 
    하지만 Closeable이 AutoCLoseable보다 더 오래된 인터페이스입니다.
    때문에, Closeable 인터페이스 부모 인터페이스인 AutoCloseable을 추가함으로써, 
    하위 호환성을 달성함과 동시에 변경 작업에 대한 수고를 덜었습니다.
    만약, Closeable을 부모로 만들었다면, 기존에 이를 사용하던 클래스들을 모두 AutoCloseable로 수정해야 합니다.

    - Closeable
      - backward compatiblity를 유지하기 위해 남아 있습니다.
      - JDK 5에 도입되었습니다.
      - `void close() throws IOException`
      - AutoCloseable의 자식 인터페이스입니다.      
    - AutoCloseable
      - try-with-resources statement를 위해 도입 되었습니다.
      - JDK 7에 도입되었습니다.
      - `void close() throws Exception`
      - Closeable의 부모 인터페이스입니다.
  </details>
  <details>
    <summary>JVM에서 예외 처리하는 흐름을 설명하세요.</summary>

    1. 예외 발생
      - JVM은 예외 객체를 생성하고 예외를 발생시킨 메서드의 호출 스택을 추적합니다.
    2. 예외 객체 전파
      - JVM은 예외를 발생시킨 메서드에서 예외 처리 코드를 찾고, 없는 경우 예외 객체를 호출 스택에서 상위 메서드로 전파합니다.
      - 예외 처리 코드 : 프로그램의 갑작스런 종료를 막고, 정상 실행을 유지할 수 있는 코드, 예를 들어 try-catch
    3. 예외 처리
      - 예외 객체가 상위로 전파되면 catch 블록을 찾고 없다면, 예외를 다시 상위 메서드로 전파합니다.
    4. 예외 처리 실패
       - 상위에서도 catch가 없으면 JVM은 처리하지 못한 것으로 판단하고 해당 예외를 처리할 수 있는 DefaultExceptionHandler를 호출합니다.
    5. DefaultExceptionHandler 실행
       - 예외 객체에 대한 정보, 예외를 처리하거나 스냅샷 정보를 수집해 디버깅을 위한 정보로 제공합니다.   
  </details>
  <details>
    <summary>예외처리가 성능에 큰 영향을 미치나요? 만약 그렇다면, 어떻게 하면 부하를 줄일 수 있을까요? (답변 미작성)</summary>
  </details>

  ---
</details>
<details>
  <summary><b>static에 대해 설명해주세요.</b></summary>

  - 공유되는 변수나 메서드를 정의할 때 사용되는 키워드입니다. 즉, 정적(=클래스) 멤버인 정적 필드나 정적 메서드를 정의할 때 사용됩니다.
  - static은 런타임 시, 클래스 로더에 의해서 Method Area 혹은 Heap 영역에 클래스 메타 데이터 및 정적 변수로 적재됩니다.
  - Static 객체는 Java 8이전에 Permanent 영역, 이후에는 Heap 영역에서 관리됩니다.
  - 대부분의 static은 런타임에 적재되고 프로그램 종료까지 GC 대상이 아니지만, Java 8 이후부터 Static 객체는 Heap 영역에 저장되고 <br/>
    주소값은 metaspace에서 관리되기 때문에, 참조를 잃은 Static 객체는 GC 대상이 될 수 있습니다.

  ---

  <details>
    <summary>인스턴스 변수, static 변수와 static 메서드를 비교해 주세요.</summary>

    - 인스턴스 변수(non-static 변수)
      - 클래스 내에 선언된 변수를 말합니다.
      - 객체 생성 시마다 매번 새로운 변수가 생성됩니다.
      - 클래스 변수와 달리 공유되지 않습니다.
    - static 변수
      - 특정 클래스에서 공용으로 함께 사용할 수 있는 변수를 만들고자 하는 경우 사용됩니다.
      - 힙 영역이 아닌, 메서드 영역에 저장되며, 클래스 당 단 하나만 생성됩니다.
      - 접근의 경우 클래스, 인스턴스 둘 다 가능하지만, 클래스 접근을 권장합니다.
    - static 메서드
      - 인스턴스 변수가 별도로 필요하지 않고, 단순히 기능만 제공할 때 사용됩니다.
      - static 메서드 내에서는 static method와 static 변수만 사용 가능합니다.
  </details>
  <details>
    <summary>static 사용을 왜 지양해야 할까요?</summary>

    - `메모리가 낭비`됩니다.
      - 대부분의 static은 프로그램 실행 시점에 메모리에 할당하며, 프로그램 종료 시점까지 메모리에서 해제되지 않기 때문입니다.
    - `별도의 동기화 전략을 수립`해야 합니다.
      - static은 전역에서 접근이 가능하기 때문입니다.
      - 전역에서 접근 가능하므로, 가변보다는 불변으로 선언하는 것이 좋습니다.
      - 만약, 동시성을 제어해 Thread-safe하게 구현한다면 성능이 떨어지게 됩니다.
    - `런타임 다형성이 불가능`합니다.
      - static으로만 이뤄진 메서드를 사용하는 객체는 메모리를 할당해서 사용하지 않고 해당 메서드에 바로 접근하여 호출하기 때문입니다.
    - `객체 상태를 이용할 수 없습니다.`
      - 대부분 static은 프로그램 실행 시점에 메모리에 올라가므로, 정적 메서드 안에서 초기화되지 않은 필드를 사용하면, 문제가 생길 수 있습니다. 
        즉, 정적 메서드 안에선 정적 변수만 사용할 수 있습니다.
      - 반대로, 정적 메서드가 아닌 일반 메서드들은 객체 내의 상태를 통해 메서드를 구현해줄 수 있으므로 상태에 따라 다양한 구현이 가능합니다.
        즉, 객체 내에 정적 메서드가 많을 수록 외부 값에 의존하는 수동적인 객체가 됩니다.
    - `테스트하기가 어렵습니다.`
      - 정적 변수는 전역으로 관리되기 때문에, 프로그램 전체에서 이 필드에 접근하고 수정할 수 있습니다.
        즉, 해당 필드를 추론하기 어려워 테스트하기가 까다롭습니다.
  </details>
  <details>
    <summary>그렇다면, static은 어떤 시점에 사용해야 하고, 사용 시, 어떤 이점을 얻을 수 있나요?</summary>

    - 자주 사용되는 상수를 정의할 때 사용할 수 있습니다.
      - `private static final` 키워드를 이용해 불변 변수인 상수를 정의하여 메모리를 아낄 수 있습니다.
    - 유틸리티 클래스를 정의할 때 사용할 수 있습니다.
      - 인스턴스 메서드와 인스턴스 변수를 제공하지 않고, 데이터 처리만을 위한 정적 메서드인 유틸리티 클래스를 정의하여 유용하게 사용할 수 있습니다.
      - 즉, 객체 상태가 필요 없고 여러 객체에서 데이터를 처리하는 공통 로직이 필요할 때 사용할 수 있습니다.
      - 예를 들어, Java의 Math Class는 상수 외에 인스턴스 변수가 하나도 없고 오로지 계산을 위한 정적 메서드만 제공합니다.
  </details>
  <details>
    <summary>static이 저장되는 위치는 어디인가요?</summary>

    static으로 선언된 변수는 Class Variables 영역에 저장됩니다.
    만약, final이 함께 사용된다면, Constant Pool에 값이 복사되어 값 조회 시, 바로 조회하기 때문에, 성능을 높여줍니다.

    - Java 8 이전
      - 8 이전의 Heap을 보면 Permanent 영역이 존재하고 이 안에 클래스 메타 데이터, 정적 변수 등이 저장됩니다.
      - 이때, Permanent 영역은 Method Area에 해당하므로 Java 8 이전의 static 변수는 메소드 영역에 저장되는 것이 맞습니다.
    - Java 8 이후
      - 8 이후 힙은 Permanent 영역이 사라지고 해당 영역에서 관리하던 클래스 메타 데이터는 Heap 외부의 Metaspace라는
        네이티브 메모리에 관리되도록 바뀌었고, String Pool과 클래스 정적 변수는 Heap 영역에서 관리되도록 바뀌었습니다.
      - 즉, Java 8 이후부터 static은 Heap 영역에서 관리됩니다. (참고: string pool은 Java 7부터)

    - Permanent 영역
      - 클래스 내부의 메타 데이터를 저장하는 영역
      - Heap 영역에 속하며, Class, Method Meta Data, Static Object, Variable, Constant Pool 등을 관리
      - Java 8 이전에는 Method Area로 사용.
      - Java 8 이후 이 영역은 사라지고 Metaspace 영역으로 대체
    - Metaspace 영역
      - Java 8부터 생긴 영역으로 Permanent 영역이 관리하던 정보를 저장.
      - Permanent 영역과는 다르게 Native Memory 영역으로서 JVM이 아닌 OS에서 관리
      - Method Area이 이 영역에 속한다.

    - Class Metadata
      - Method Area에 저장되는 정보 단위
      - Class Metadata가 저장되는 Method Area(Metaspace)는 Heap 영역에서 관리되기 때문에, 
        static 변수를 참조하지 않는 상황이 오면 GC 대상이 될 수 있습니다.
      - 즉, Class Metadata가 GC 대상이 되면, 자동적으로 static 변수들도 GC 대상이 됩니다.
    - Method Area에 저장되는 정보
      - Type 정보 : name, sub class name, modifier 등
      - Field 정보 : type, modifier 등
      - Method 정보 : Construtor를 포함한 모든 메소드 메타 데이터
      - Runtime Constant Pool : Type, Field, Method의 모든 레퍼런스 정보
                                JVM은 이 영역을 통해, 실제 메모리 상 주소를 찾아 참조합니다.
      - Class Variable : static 키워드로 선언된 변수를 저장합니다. 
                         클래스 변수를 관리하는 곳이기 때문에, 모든 인스턴스에 공유되며 인스턴스 없이 접근이 가능합니다.
                         final static 변수는 상수로 치환되어 Method Area의 Constant Pool에 값을 복사합니다.
                         클래스를 사용하기 이전에 이 변수들은 미리 메모리를 할당 받습니다.
  </details>
  <details>
    <summary>static 키워드 동작 흐름을 설명해주세요.</summary>

    [정리]
      1-1. static만 선언된 경우 Class Variables 영역에 값을 참조합니다.
      1-2. static만 선언된 경우 동시성 이슈가 발생할 수 있습니다.
      1-3. thread-safe하게 한다면 성능 이슈가 발생합니다.
  
      2-1. static과 final로 선언된 경우, Constant pool 영역에 값을 참조합니다.
      2-2. thread-safe하고 성능 이슈도 발생하지 않게 됩니다.

      3-1. Constant Pool에 복사된 값이 수정이 일어나면 Class Metadata를 갱신해야하기 때문에, 가변 변수는 따로 관리합니다.
      3-2. lazy-loading으로 static 변수 초기화 시점을 조절해 메모리를 효율적으로 사용할 수 있습니다.

    [static 키워드만 사용된 변수 호출 동작 흐름]
      - 메모리 할당 및 초기화 단계
        1. 클래스로더에 의해 메모리를 할당받고 static initializer에 의해 값을 초기화합니다.
        2. 메모리 영역의 Class Variable 영역에 변수값이 저장됩니다.
        3. 클래스의 Constant Pool에 Class Variable의 참조 값이 저장됩니다.
      - 호출 단계
        1. Constant Pool의 메모리 공간의 시작 지점을 조회합니다.
        2. Constant Pool에 저장된 참조 값을 읽습니다.
        3. Class Variables에서 실제 값을 읽습니다.
    [static과 final 키워드가 사용된 변수 호출 동작]
      - 메모리 할당 및 초기화 단계
        1. 선언된 변수는 메모리를 할당받고 static initializer에 의해 값을 초기화합니다.
        2. 메모리 영역의 Class Variable 영역에 실제 값이 저장됩니다.
        3. 클래스의 Constant Pool에 Class Variable의 실제 값이 복사됩니다.
      - 호출 단계
        1. Constant Pool의 메모리 공간의 시작 지점을 조회합니다.
        2. Constant Pool에 저장된 실제 값을 읽습니다.
    [왜, 차이가 발생할까?]
      - Constant Pool에 복사된 값을 수정하는 연산이 진행되면, Class Metadata를 갱신해야 하고,
        데이터 정합성을 위해 생기는 락에 의해 성능이 떨어질 수 있기 때문입니다.
      - 즉, 변경 가능성이 있는 변수를 따로 관리한다고 볼 수 있습니다.
    [static 변수가 바로 초기화되지 않는 상황]
      - static 변수들이 초기화되는 시점은 항상 클래스의 인스턴스가 생성되는 시점이라고 볼 수 없습니다.
        즉, static 변수를 Lazy Loading해 효율적으로 메모리를 사용할 수 있습니다.
      - 예를 들어, static 메서드는 호출 시점에 초기화되는 방식을 이용해 static variables가 선언된 inner class 인스턴스 생성을 제어하면,
        static 변수의 초기화 시점을 원하는 순간으로 조절할 수 있습니다.
  </details>
  <details>
    <summary>Java 8이후로 Heap의 Permanent(PermGen) 영역이 Native Memory 영역의 Metaspace로 대체된 이유는? </summary>
    
    - 결론부터 말씀드리면, OOM(OutOfMemory) 에러의 발생 가능성을 줄이기 위해서입니다.
    - PermGen은 고정 메모리 사이즈를 가지고 있기 때문에, MAX 값이 반드시 설정해야 해서 메모리 관리의 불편함이 있었습니다.
      만약, MAX 값을 설정하지 않으면 Default 값이 설정됩니다.
    - 어쨌든, 이 MAX 값을 넘어서는 순간, OOM이 발생하는데, 이 문제점을 해결하기 위해 Metaspace로 대체된 것입니다.
    - Metaspace의 메모리 MAX 값은 기본값이 64 bit Integer의 최댓값이기 때문에, 특별한 경우가 아닌 이상 신경쓰지 않아도 됩니다.
  </details>
  <details>
    <summary>컴파일 과정에서 static 이 어떻게 처리되는지 설명해주세요.</summary>

    - static 키워드가 붙은 멤버는 클래스 로딩 시점(런타임 시점)에 메모리에 할당됩니다.
    - 이는 컴파일 과정에서 이뤄지는 것이 아닌 JVM이 클래스를 로딩하고 초기화하는 과정에서 이뤄집니다.
    - static 키워드가 붙은 멤버는 클래스 레벨에서 관리되기 때문에, 해당 클래스의 모든 인스턴스에서 동일한 멤버에 접근할 수 있습니다.
  </details>
  <details>
    <summary>main 메서드가 static인 이유를 아시나요?</summary>
    
    - 프로그램 실행 순간에 메모리에 할당되어야 하고 GC의 정리 대상이 되어서는 안되기 때문입니다.
  </details>
  
  ---
</details>
<details>
  <summary><b>final에 대해 설명해주세요.</b></summary>

  - 자바에서 불변성을 확보할 수 있도록 제공하는 키워드입니다.
    - final Variables, Arguments : 불변값이 되도록 합니다.
    - final Class : 상속받지 못하도록 합니다.
    - final Method : 오버라이딩이 되지 못하도록 합니다.
    
  ---
  
  <details>
    <summary>final 키워드를 사용하면, 어떤 이점이 있나요?</summary>

    - 최초 할당 후 해당 값을 변경할 수 없어 안정성을 높이고, 버그를 방지할 수 있습니다.
  </details>
  <details>
    <summary>Effective Final 키워드에 대해 아시나요?</summary>

    - 변수에 final 키워드를 사용하지 않아도 초기화 후 변경되지 않는 변수라면, 컴파일러가 final 변수로 인식하는 것을 말합니다.
    - 이는 Lambda가 final을 명시하지 않은 지역 변수를 사용할 수 있도록 하기 위해 Java 8이후로 도입된 기능입니다.
  </details>
  <details>
    <summary>익명 클래스나 람다 표현식에서 외부 지역변수를 참조할 때, final 혹은 effective final이어야 하는 이유가 있나요?</summary>

    - 멀티 스레드에서는 지역 변수를 사용하는 스레드와 람다식을 사용하는 스레드가 다를 수 있습니다.
      예를 들어, 지역변수는 클래스 변수나 인스턴스 변수와는 달리, 각 스레드의 스택 프래임에 독립적으로 생성됩니다.
      즉, 다른 스레드를 사용하는 람다식에선 해당 지역변수의 최신값을 동기화할 수 있어서 변경 가능성이 없어야 합니다.
  </details>
  <details>
    <summary>final은 완벽한 불변을 보장하나요?</summary>

    - 아닙니다. final은 변수의 재할당은 막지만, 참조하고 있는 객체 내부 상태의 불변은 보장하지 못합니다.
      예를 들어, final 키워드로 ArrayList 타입의 변수를 선언해도 add() 메서드를 통해 내부에 값을 추가할 수 있습니다.
  </details>
  <details>
    <summary>그렇다면, 어떻게 불변성을 보장할까요?</summary>

    - 객체의 경우에는 생성자를 통해 값을 주입받도록 합니다.
    - 컬렉션의 경우에는 Unmodifiable Collection을 활용하거나 직접 복사해서 사용하는 것도 하나의 방법입니다.
  </details>
  <details>
    <summary>컴파일 과정에서, final 키워드는 다르게 취급되나요?</summary>

    - final 키워드가 붙은 변수는 컴파일러에 의해 한 번만 초기화될 수 있음을 표시하는 것입니다.
      즉, 이는 불변성을 보장하는 키워드입니다. 
    - 예를 들어, 해당 키워드 사용 시, 해당 변수가 한 번 초기화 된 후 다시 값을 변경하는 코드가 있는 지 검사 후,
      있다면 컴파일 에러가 발생합니다.
  </details>
  <details>
    <summary>finally와 finalize 용어도 간단하게 설명해주세요.</summary>

    - finally는 try-catch 블록이 종료될 때, 실행될 코드 블록을 정의하기 위해 사용합니다.
    - finalize는 GC가 더 이상 참조하지 않는 객체를 메모리에서 삭제하겠다고 결정하는 순간 호출됩니다.
  </details>

  ---
</details>
<details>
  <summary><b>generic에 대해 설명해주세요.</b></summary>

  - 타입을 클래스 내부에서 지정하는 것이 아닌 외부에서 사용자에 의해 지정하는 기능입니다.
  - 예를 들어, 변수 선언 시 타입을 지정해주듯, 재네릭은 객체에 타입을 지정해주는 것입니다.
  - 이 기능은 JDK 1.5에 추가된 Spec입니다.

  ---
    
  <details>
    <summary>제네릭 사용 이유 및 이점을 설명해주세요.</summary>

    - JDK 1.5 이전에는 여러 타입을 다루기 위해 인수나 반환값으로 Object 타입을 사용했었습니다.
        하지만, 이 방식은 Object 타입 객체를 다시 원하는 타입으로 일일히 타입 변환을 해야하고 
        런타임 에러가 발생할 가능성도 존재했습니다.

    - 컴파일 단계에 타입 검사를 통한 예외 방지
      - 제네릭은 컴파일 시점에서 클래스나 메서드를 정의할 때, 타입 파라미터로 객체의 서브 타입을 지정해줌으로써,
        잘못된 타입이 사용될 수 있는 문제를 컴파일 단계에서 찾을 수 있습니다.
    - 불필요한 캐스팅을 없애 성능 향상
      - 미리 타입을 지정 및 제한해놓기 때문에 형변환의 번거로움을 줄일 수 있습니다.
      - 또한, 타입 검사에 들어가는 메모리를 줄일 수 있고 더불어 가독성도 좋아집니다.
  </details>
  <details>
    <summary>제네릭 사용 시, 주의사항 및 단점을 말씀해주세요. (답변 미작성)</summary>

  </details>
  <details>
    <summary>와일드 카드 문법에서 extends와 super 키워드는 어디서 사용될 수 있을까요? (답변 미작성)</summary>

  </details>
  <details>
    <summary>제네릭 타입 소거 컴파일 과정에 대해서 아시나요? (답변 미작성)</summary>

  </details>

  ---
</details>
<details>
  <summary><b>Java Stream에 대해 설명해 주세요.</b></summary>

  - Java 8에 추가된 것으로 데이터를 쉽게 필터링, 변환, 집계할 수 있는 기능입니다.
  - 이는 선언형으로 컬렉션 데이터를 간결하고 가독성 좋게 처리가 가능합니다.

  ---

  <details>
    <summary>스트림의 특징을 말해주세요.</summary>

    - 파이프라이닝
      - 스트림 연산끼리 연결하여 커다란 파이프라인을 구성할 수 있습니다.
      - 대부분의 스트림 연산은 자신을 반환하기 때문에 파이프라이닝이 가능합니다.
    - 내부 반복
      - 명시적으로 반복자를 통해 반복하지 않고, 스트림 내부에서 일어나는 반복을 수행합니다.
      - 즉, for 혹은 while을 사용하지 않아도 됩니다.
  </details>
  <details>
    <summary>스트림의 연산과 흐름에 대해 설명하세요.</summary>

    - 중간 연산
      - 스트림을 연결할 수 있는 연산을 말합니다.
      - Ex) filter, sorted, map 등처럼 다른 스트림을 반환합니다.
    - 최종 연산
      - 스트림을 닫는 연산을 말합니다.
      - Ex) void, array, list 등 스트림 외의 값을 반환합니다.
    - 흐름
      1. 가장 먼저 소스를 지정합니다.
      2. 이후 중간 연산을 연결해 파이프라인을 구성합니다.
      3. 파이프라인을 실행하여 최종 연산으로 결과값을 반환합니다.
  </details>
  <details>
    <summary>Stream과 foreach 기능에 대해 설명해주세요.</summary>

    - 이는 모두 순회하는 기능으로 강제 종료가 불가능합니다.
    - foreach 내부에서 로직이 추가되면 동시성이나 가독성이 떨어집니다.
  </details>
  <details>
    <summary>Stream과 for ~ loop의 성능 차이를 비교해 주세요. (답변 미작성)</summary>
  </details>
  <details>
    <summary>Stream은 병렬처리 할 수 있나요? (답변 미작성)</summary>
  </details>

  ---
</details>
<details>
  <summary><b>Java Lambda에 대해 설명해 주세요.</b></summary>

  - 함수를 하나의 식으로 표현하는 기능을 말합니다.
  - 이 기능은 익명 함수를 지칭합니다. 이는 이름이 없는 함수를 의미하며, 일급 객체라는 특징을 가지고 있습니다.
  - 추가적으로 람다식 내부에서 사용되는 지역 변수는 상수로 간주되고 람다 변수명은 다른 변수명과 중복될 수 없습니다.

  ---
  
  <details>
    <summary>람다의 장/단점을 설명하세요.</summary>

    - 장점
      - 코드를 간결하게 만들고 식 자체에 의도가 명확해 가독성을 높입니다.
      - 함수를 만드는 과정없이 한 번에 처리할 수 있어 생산성이 높아집니다.
      - 병렬 프로그래밍에 용이합니다.
    - 단점
      - 만든 함수는 재사용이 불가능합니다.
      - 디버깅이 어렵습니다.
      - 재귀로 만들 경우 부적합합니다.
  </details>
  <details>
    <summary>일급 객체란 무엇인가요?</summary>

    - 다른 객체들이 적용 가능한 연산을 모두 지원하는 객체를 의미합니다. 즉, 함수를 값으로 사용할 수 있어야 합니다.
    - 예를 들어, 변수나 데이터에 담을 수 있고, 파라미터 전달 가능 및 반환값으로 사용이 가능해야 합니다.
  </details>
  <details>
    <summary>함수형 인터페이스에 대해 설명해 주세요.</summary>

    - 함수를 일급 객체처럼 이용할 수 있도록 해주는 어노테이션입니다.
      - Supplier T : 매개변수 없이 반환 값만을 갖는 함수형 인터페이스
      - Consumer T : 객체 T를 받아 사용하며 반환 값이 없는 함수형 인터페이스
      - Function T, R : 객체 T를 받아 처리 후 R로 반환하는 함수형 인터페이스
      - Predicate T : 객체 T를 받아 처리 후 Boolean을 반환하는 함수형 인터페이스
  </details>
  <details>
    <summary>익명 클래스나 람다 표현식에서, 주의해야할 점을 말해주세요.</summary>

    - final이거나 effective final인 경우에만 참조할 수 있습니다.
      그렇지 않은 경우, 동시성 문제가 생길 수 있기 때문에, 컴파일러 단계에서 에러가 발생합니다.
    - 람다 표현식은 익명 클래스 구현체와 달리 쉐도잉하지 않습니다. 
      예를 들어, 익명 클래스는 새로운 영역을 만들지만, 람다는 람다를 감싸고 있는 영역과 같습니다.
  </details>
  
  ---
</details>
<details>
  <summary><b>Reflection에 대해 설명해 주세요.</b></summary>

  - 클래스의 구체적인 타입을 알지 못해도 해당 클래스에 접근할 수 있도록 해주는 자바 API 기능입니다.

  ---

  <details>
    <summary>의미만 들어보면 리플렉션은 보안적인 문제가 있을 가능성이 있어보이는데, 어떻게 방지할 수 있을까요? (답변 미작성)</summary>
  </details>
  <details>
    <summary>리플렉션의 장/단점에 대해 설명하세요.</summary>

    - 장점
      - 런타임 시점에 클래스 인스턴스를 생성하고 접근 제어자와 관계없이, 
        필드와 메서드에 접근해 필요한 작업을 수행할 수 있는 유연성을 가집니다.
    - 단점
      - 캡슐화가 깨집니다.
      - 런타임 시점에 클래스를 분석하기 때문에, 존재하지 않는 클래스명의 경우 실행 시에 오류가 발생합니다.
      - JVM 최적화가 불가능합니다.
        - 일반적으로 메서드는 컴파일 단계에 분석된 클래스를 활용하는데, 리플렉션은 런타임 시점에 클래스를 분석해 속도가 느립니다.
        - JIT 컴파일러는 클래스 타입을 모르기 때문에, 매번 명시된 클래스 타입이 맞는지, 생성자가 존재하는 지 검증해야 합니다.
  </details>
  <details>
    <summary>실제로 어디서 리플렉션이 활용되고 있을까요?</summary>

    - 스프링 컨테이너인 BeanFactory
      - 빈은 애플리케이션 실행 후 런타임에 객체가 호출될 때, 동적으로 객체의 인스턴스를 생성합니다.
      - 예를 들어, 스프링에서 @Controller, @Service 같은 어노테이션을 붙이면 BeanFactory에서 해당 어노테이션이 붙은 클래스를 생성하고 관리합니다.
      - 즉, 리플렉션을 통해 클래스의 인스턴스를 생성하고 필요한 필드를 주입해 BeanFactory에 저장하여 사용하는 것을 알 수 있습니다.
    - Spring Data JPA
      - 리플렉션 API로는 생성자의 인자 정보는 가져올 수 없습니다.
      - 때문에, 리플렉션 API를 활용하는 JPA에서는 동적으로 객체 생성 시, Entity에 기본 생성자가 반드시 있어야만, 객체를 생성할 수 있습니다.
    - Dynamic Proxy
      - Dynamic Proxy는 런타임 시점에 프록시 클래스를 만들어줍니다.
      - Dynamic Proxy는 JDK에서 지원하는 프록시를 생성합니다.
      - Dynamic Proxy는 리플렉션 API를 사용합니다.
      - invocationHandler를 구현한 invoke() 메서드를 정의해야 합니다.
      - 인터페이스가 반드시 있어야 합니다.
  </details>
  <details>
    <summary>그렇다면, 리플렉션을 언제 활용할 수 있을까요? </summary>

    1. 동적으로 클래스를 사용해야 하는 경우
      - 코드 작성 시점에 어떤 클래스를 사용해야할 지 몰라서, 런타임에 클래스를 가져와야하는 상황에 사용할 수 있을 것 같습니다.
      - 예를 들어, 스프링의 어노테이션이 있습니다.
    2. Jackson, GSON 등의 JSON 직렬화 라이브러리
    3. private인 메서드에 대한 테스트 코드를 작성해야 하는 경우
  </details>
  <details>
    <summary>Dynamic Proxy에 대해 설명해 주세요.</summary>

    - 동적으로 프록시 인스턴스를 만들어 등록하는 방법을 말합니다.
    - 이는 InvocationHandler를 구현하여 invoke() 메서드를 오버라이딩하고 method.invoke()를 통해 기존 클래스 메서드를 실행합니다.
    - 동적 프록시는 반드시 타입을 클래스가 아닌 인터페이스를 파라미터로 넣어야 합니다.
  </details>
  <details>
    <summary>Dynamic Proxy 동작 과정에 대해 설명해 주세요. (답변 미작성)</summary>
  </details>
  
  ---
</details>

## Java Collection

<details>
  <summary><b>equals()와 hashcode()에 대해 설명해 주세요.</b></summary>

  - equals()
    - Object의 equals()의 경우 객체의 참조값이 동일한 지 비교합니다.
    - 동등성 비교를 위해서는 equals() 메서드를 오버라이딩해서 사용해야 합니다.
    - String과 특정 클래스들은, 이미 내부에서 주소값이 아닌 내용을 비교하도록 오버라이딩되어 있습니다.
  - hashcode()
    - Object의 hashcode()는 각 객체의 주소 값을 해싱하여 해시 코드를 만든 후 반환합니다.
    - equals()의 결과가 true인 경우 두 객체의 해시코드는 반드시 같아야 합니다.
    - equals()의 결과가 false의 경우 두 객체의 해시코드가 꼭 다를 필요는 없습니다. <br/>
      단, 달라야 해시 테이블 성능이 좋아집니다.
    
  ---

  <details>
    <summary>동등성과 동일성을 비교해주세요.</summary>

      - 동일성
        - 객체 주소를 비교합니다.
      - 동등성
        - 값 자체를 비교합니다.
  </details>
  <details>
    <summary>hashcode() 를 정의해야 한다면, 어떤 점을 염두에 두고 구현할 것 같으세요?</summary>

    - equals 비교에 사용되는 핵심 필드들을 이용해 hashcode()를 반환하도록 구현할 것 같습니다.
      - 핵심 필드가 변경되지 않았다면, 해시 코드 값을 일관되게 반환하도록 할 것 같습니다.
      - equals()가 true이면 hashcode() 반환값도 동일하도록 구현할 것 같습니다.
  </details>
  <details>
    <summary>equals() 를 재정의해야 할 때, 어떤 점을 염두에 두어야 하는지 설명해 주세요.</summary>

    1. 반사성) null 이 아닌 모든 참조값 x에 대해 : x.equals(x) == true
    2. 대칭성) null 이 아닌 모든 참조값 x,y에 대해 : x.equals(y) == true -> y.equals(x) == true
    3. 추이성) null 이 아닌 모든 참조값 x,y,z에 대해 : x.eqauls(y) == true && y.equlas(z) == true -> x.eqauls(z) == true
    4. 일관성) null 이 아닌 모든 참조값 x,y에 대해 : 반복해서 호출했을 때, 항상 x.equals(y) == true 또는 x.equals(y) == false
    5. null-아님) null이 아닌 모든 참조값 x, y에 대해 : x.equals(null) == false
  </details>
      
  ---
</details>
<details>
  <summary><b>Synchronized 키워드에 대해 설명해 주세요.</b></summary>

  - 자바에서 제공하는 것으로 특정 코드 블록 및 메서드 영역에 하나의 스레드만 접근할 수 있도록 하여, 스레드 간에 동기화를 제공하는 기능입니다.

  ---
  
  <details>
    <summary>Synchronized 키워드가 어디에 붙는지에 따라 의미가 약간씩 변화하는데, 각각 어떤 의미를 갖게 되는지 설명해 주세요.</summary>

    - 메서드
      - 메서드 전체를 임계 영역으로 지정합니다.
      - 즉, 쓰레드는 해당 키워드가 붙은 메서드가 호출된 시점부터 해당 메서드가 포함된 객체의 락을 얻어, 
        작업을 수행하다가 메서드 종료 시, 락을 반환합니다.
    - 특정 코드 블록
      - 이 블록 영역 안으로 들어가면서 쓰레드는 지정 객체의 락을 얻고 이 블럭을 벗어나면 락을 반환합니다.
  </details>
  <details>
    <summary>효율적인 코드 작성 측면에서, Synchronized는 좋은 키워드일까요? (답변 미작성)</summary>
  </details>
  <details>
    <summary>Synchronized 를 대체할 수 있는 자바의 다른 동기화 기법에 대해 설명해 주세요. (답변 미작성)</summary>
  </details>
  <details>
    <summary>Thread Safe란 무엇인가요?</summary>

    - 멀티 쓰레드 프로그래밍에서 여러 스레드로부터 동시에 접근이 이뤄져도 프로그램 실행에 문제가 없는 것을 의미합니다.
    - 이를 위해 한 쓰레드가 특정 작업을 끝마치기 전까지 다른 쓰레드에 의해 방해받지 않도록 임계영역과 잠금 개념이 도입되었습니다.
      - 임계 영역 : 공유 데이터를 사용하는 코드 영역
      - 잠금 : 공유 데이터를 사용하는 코드 영역을 잠금하여 락을 획득
      - 쓰레드 동기화 : 임계 영역 설정 후 락을 획득한 하나의 쓰레드만 영역 내 코드를 수행하고 수행을 마치면 락 반납 후 다음 쓰레드가 락을 획득합니다.
  </details>
  <details>
    <summary>Thread Local에 대해 설명해 주세요. </summary>

    - 스레드 영역에 변수를 설정해 특정 스레드가 실행하는 모든 코드에서 설정된 변수값을 사용할 수 있게 하는 기능입니다.
    - Ex) Spring SecurityContextHolder
  </details>
  <details>
    <summary>Volatile에 대해 설명해주세요.</summary>

    - 원자성은 보장할 수 없지만, 가시성을 보장하는 기능입니다.
  </details>
  <details>
    <summary>가시성이란 무엇인가요?</summary>

    - 가시성
      - 한 쓰레드에서 공유 자원을 변경한 결과가 다른 쓰레드에서 확인할 수 있는 것을 의미합니다.
    - 원자성
      - 명령이 수행되는 동안 다른 쓰레드에서 접근이 불가능하게 만들어 동시 접근 문제를 보장하는 것을 의미합니다.
  </details>
  <details>
    <summary>Atomic에 대해 설명해주세요.</summary>

    - synchronized 키워드의 성능 저하 문제를 해결하기 위해 고안된 방법입니다.
    - 원자성을 보장하는 변수를 의미합니다.
  </details>
  <details>
    <summary>AtomicInteger에 대해 설명해주세요. (답변 미작성)</summary>
  </details>
  
  ---
</details>
<details>
  <summary><b>String에 대해 설명해 주세요.</b></summary>

  - String은 문자열을 저장하는 자료형으로 불변합니다. 즉, 할당된 공간이 변하지 않는 '불변' 문자열 자료형입니다.
  - String 객체의 내부 구성 요소에는 value 값이 상수(final)로 되어있습니다.
    
  ---

  <details>
    <summary>자바에서 String을 불변으로 설정한 이유를 아시나요?</summary>
    
    - 캐싱
      - String을 불변하게 함으로써 String pool에 각 리터러 문자열의 하나만 저장합니다.
      - 이는 다시 사용하거나 캐싱에 이용 가능하며 이로 인해 힙 공간을 절약할 수 있다는 장점이 있습니다.
    - 보안
      - 예를 들어, 데이터베이스 사용자 이름, 암호는 데이터베이스 연결을 수신하기 위해 문자열로 전달되는데, 
        만일 문자열 값이 변경이 가능하다면 참조 값을 변경하여 보안 문제를 일으킬 수 있습니다.
    - 동기화
      - 불변함으로써, 동시에 실행되는 여러 스레드에서 안정적이게 공유가 가능합니다.
  </details>
  <details>
    <summary>String, StringBuffer, StringBuilder 차이점을 설명해주세요.</summary>

    - String
      - String 클래스는 Immutable Object입니다.
      - 문자열을 연결하거나 수정할 때마다 새로운 String 객체가 생성되므로 메모리 사용량이 증가할 수 있습니다.
      - 불변 객체이기 때문에, 멀티스레드 환경에서 안전합니다.
    - StringBuilder
      - String과 같이 문자열을 다루지만, 객체 공간이 부족해지는 경우 버퍼 크기를 유연하게 늘려주는 Mutable Object입니다.
      - 내부 버퍼에 문자열을 저장하고 그 안에서 추가, 삭제, 삭제 작업을 할 수 있습니다.
      - 한 번 생성 시, 불변 특성으로 인해 매 연산마다, 새로운 인스턴스를 생성하는 String과 달리 가변성을 가지기 때문에, 동일 객채 내에서 크기 변경이 가능합니다.
      - String은 euqals()로 값 비교가 가능하지만 이는 equals를 오버라이딩하지 않아 비교가 불가능합니다. 즉, toString()으로 꺼낸 후 비교해야 합니다.
      - 멀티스레드 환경에서 안전하지 않지만, 단일 스레드 환경에서는 StringBuffer보다 StringBuilder를 사용하는 것이 더 효율적입니다.
    - StringBuffer    
      - String과 같이 문자열을 다루지만, 객체 공간이 부족해지는 경우 버퍼 크기를 유연하게 늘려주는 Mutable Object입니다.
      - 내부 버퍼에 문자열을 저장하고 그 안에서 추가, 삭제, 삭제 작업을 할 수 있습니다.
      - 한 번 생성 시, 불변 특성으로 인해 매 연산마다, 새로운 인스턴스를 생성하는 String과 달리 가변성을 가지기 때문에, 동일 객채 내에서 크기 변경이 가능합니다.
      - String은 euqals()로 값 비교가 가능하지만 이는 equals를 오버라이딩하지 않아 비교가 불가능합니다. 즉, toString()으로 꺼낸 후 비교해야 합니다.
      - 메서드 내에서 synchronized 키워드를 사용해 동기화를 지원하기 때문에, 멀티스레드 환경에서 안전하게 사용할 수 있습니다.
  </details>
  <details>
    <summary>Immutable Object에 대해 설명해주세요.</summary>

    - 객체 생성 이후 내부 상태가 변하지 않는, 변경할 수 없는 객체를 의미합니다.
    - 대표적으로 String, Integer, Wrapper 클래스가 있습니다.
    - 불변 객체는 내부 상태를 변경하는 메서드를 제공하지 않거나 방어적 복사를 통해 데이터를 제공합니다.
  </details>
  <details>
    <summary>Immutable Object의 장점을 말해주세요.</summary>

    - Thread-safe하여 동기화를 고려하지 않아도 됩니다.
    - 값이 덮어씌워지는 문제가 없고 항상 동일한 값 보장합니다.
    - 내부 상태의 변경이 없기 때문에 Cache, Map, Set 등의 요소로 활용하기에 적합합니다.
    - 요소가 변경되지 않기 때문에 갱신 작업이 필요 없습니다.
    - 외부에서 객체에 대해 변경할 수 없기에 안정성이 높고 신뢰성이 높습니다.
    - 가비지 컬렉션의 성능을 높일 수 있음.
    
    [Oracle]
      - 객체 생성에 대한 비용은 과대 평가 되고 있습니다. -> 불변 객체를 이용한 효율로 충분히 상쇄 가능합니다.
      - 불변 객체를 새로 생성한다 해서 GC에서 생명주기가 짧은 객체를 처리하는 것은 부담되지 않는 일입니다.
      - 불변 객체를 이용하면 불변객체 내부의 객체에 대해서는 GC 스캔 대상에 제외됩니다.
  </details>
  <details>
    <summary>`String a = ""`과 `String a = new String("")`의 차이점을 설명해주세요.</summary>

    - 리터럴 방식 : String a = ""
      - 이 방식으로 생성할 경우 Method Area 안의 Constant Pool에 저장되며,
        동일한 문자열 리터럴이 여러 곳에 사용되어도 하나의 인스턴스만 존재합니다.
    - 생성자 방식 : new String("")
      - 이 방식은 새로운 객체가 생성되므로 Constant Pool이 아닌 Heap 영역에 새로운 객체가 할당되는 방식이기 때문에,
        성능상 좋지 못합니다.
  </details>

  ---
</details>

<details>
  <summary><b>Java에서 제공되는 List, Set, Map에 대해서 설명해주세요.</b></summary>

  ---

  <details>
    <summary>Array와 ArrayList 차이에 대해 설명해주세요.</summary>

    - 공통점
      - 둘 모두 연속적으로 값을 유지하며 배열의 원소들을 이용해 관리합니다.
    - 차이점
      - Array의 크기는 고정이지만 ArrayList는 크기가 유동적입니다.
  </details>
  <details>
    <summary>ArrayList와 LinkedList의 차이에 대해 설명해주세요.</summary>

    - ArrayList
      - 중복을 허용하고 입력되는 순서를 유지하며, 배열을 사용해 원소들을 관리합니다.
      - 특정 인덱스 조회 시 O(1)으로 값을 가져올 수 있습니다. 즉, 데이터 접근은 LinkedList보다 빠르다고 할 수 있습니다.
      - 삽입/삭제 자체는 O(1)만큼 걸리지만, 삽입/삭제 시 필요한 경우 원소들을 옮기는 연산이 발생하여 O(N)만큼 추가 시간이 걸립니다.
      - 내부적으로 동적 배열을 사용해 요소들을 저장합니다. 만약 배열 확장이 필요한 경우라면 새로운 배열에 복사하는 추가 시간이 발생합니다.
      - 배열 기반이기 때문에 사용하지 않는 공간도 메모리를 차지할 수 있지만, 이 외에 추가적인 오버헤드는 없습니다.
    - LinkedList
      - 연결된 노드들의 집합이며, 각 노드는 데이터와 포인터로 이루어져있습니다.
      - 특정 노드 조회 시, 첫 노드부터 순차적으로 탐색해서 O(N)만큼 걸립니다.
      - 삽입/삭제 자체는 O(1)만큼 걸리지만, 삽입/삭제 위치로 이동하는 시간이 추가적으로 발생합니다. 
      - 삽입/삭제에 있어서는 이동 연산이 발생하는 ArrayList보다 빠르다고 볼 수 있습니다.
      - 이중 연결 리스트를 사용해 요소들을 저장하기 때문에 같은 수의 요소를 저장하더라도 ArrayList보다 더 많은 메모리를 사용할 수 있습니다.
  </details>
  <details>
    <summary>LinkedList가 ArrayList 중 선택하는 기준이 있나요?</summary>

    - 보통 삽입/삭제가 빈번하면 LinkedList를 사용하고 특정 요소 조회가 빈번하면 ArrayList를 사용한다고 말합니다.
    - 하지만 ArrayList가 리사이징 과정에서 배열 복사 비용이 추가적으로 들지만, 내부적으로 잘 튜닝이 되어 있어 큰 차이가 없는 것으로 알고 있습니다.
    - 때문에, LinkedList는 잘 사용되지 않는 것으로 알고 있고 실제로 자바를 설계하고 구현을 주도한 조슈아 블로치 본인도 잘 사용하지 않는다고 한 글을 본 적이 있습니다.
    - 또한 선입선출 빈번할 경우, ArrayList 경우 첫번째에 요소를 추가할 때마다 자주 데이터 이동이 일어나기 때문에 "큐를 사용해야 할때 LinkedList를 사용한다"라고 말하지만, 
      차라리 그런 경우엔 따로 최적화된 컬렉션인 ArrayDeque을 쓰는 것이 훨씬 좋습니다.
  </details>
  <details>
    <summary>HashMap, HashTable, ConcurrentHashMap, LinkedHashMap, TreeMap 각 차이를 설명해주세요.</summary>

    - HashMap
      - Key와 Value에 Null을 허용합니다.
      - 동기화를 보장하지 않아 Thread-safe 하지 않습니다.
      - 즉, 동기화 처리를 하지 않아 데이터 탐색 속도가 HashTable과 ConcurrentHashMap보다 빠르지만, 신뢰성과 안정성이 떨어집니다.
      - HashMap의 반복자(Iterator)는 fail-fast 속성을 가집니다.
    - HashTable
      - Key와 Value가 Null을 허용하지 않습니다.
      - 동기화를 보장해 Thread-Safe 합니다. 즉, 멀티-쓰레드 환경에서 안전합니다.
      - 예를 들어, 데이터를 다루는 메서드인 get(), put() 등에 synchrnized 키워드가 붙어 있습니다. 
        즉, 메서드 호출 전 동기락이 걸려 무결성을 보장하지만 쓰레드 간 동기락으로 인해 성능이 상대적으로 느립니다.
      - HashTable의 반복자(Iterator)는 fail-fast 속성을 가지고 있지 않습니다.
      - 내부적으로 배열과 해시 함수를 사용해 데이터를 관리합니다.
    - ConcurrentHashMap
      - Key와 Value에 Null을 허용하지 않습니다.
      - 동기화를 보장해 Thread-Safe 합니다. 즉, 멀티-쓰레드 환경에서 안전합니다.
      - 이는 HashTable처럼 Synchronized 키워드를 특정 메서드에 동기락을 제공하는 것이 아닌 특정 Entry에 대해서만 락을 겁니다.
        즉, Entry 별로 락을 걸기 때문에, HashTable보다 성능이 좋습니다.
      - 예를 들어, 이 컬렉션은 동시성에 삽입/삭제와 같은 수정에만 동기화되고 읽기 작업은 동기락을 걸지 않습니다.
    - LinkedHashMap
      - Key와 Value에 Null을 허용합니다.
      - 배열 안에 구현되어 있는 노드에 이전 노드 값과 이후 노드 값을 가지고 있어 순서를 유지하는 HashMap입니다.
      - 즉, 순서 보장에 필요한 값들이 추가적으로 관리되기 때문에 더 많은 메모리 비용이 발생합니다.
      - 동기화를 보장하지 않아 Thread-safe 하지 않습니다.
    - TreeMap
      - Key는 Null을 허용하지 않고 Value에는 Null을 허용합니다.
      - 이곳에 객체를 저장하면 저장과 동시에 오름차순으로 정렬됩니다. 
      - 예를 들어, 부모 키값과 비교해서 키 값이 낮은 것은 왼쪽 자식 노드로, 큰 것은 오른쪽 자식 노드에 객체를 저장합니다.
      - 보통 정렬된 상태를 유지하기 위해서나 범위 탐색이 필요한 경우 사용하는 Map 컬렉션입니다.
      - 이진 트리를 기반으로 구현된 Map 컬렉션으로 내부적으로는 레드-블랙 트리의 자료구조를 이용하고 있습니다.
  </details>
  <details>
    <summary>fail-fast 속성이란 무엇인가요?</summary>

    - 오류를 가능한 빨리 감지하고 오류 발생 시, 즉시 작업을 중단해 더 큰 시스템 장애로 이어지는 것을 방지하는 것을 말합니다. 
    - fail-fast 반복자는 내부적으로 컬렉션의 수정 횟수를 추적합니다. 즉, 자바 컬렉션 프레임워크에서 컬렉션을 순회하는 동안 
      해당 컬렉션이 수정될 경우 즉각적으로 ConcurrentModificationException을 던지는 반복자의 속성을 가르킵니다.
    - 예를 들어, 반복자가 생성된 후 컬렉션에 어떤 변경사항이 생겼을 때, 수정 횟수와 내부의 카운트가 불일치하게 되면
      ConcurrentModificationException을 발생시켜 동시 수정이 일어났음을 알립니다.
  </details>
  <details>
    <summary>HashMap과 HashTable이 내부적으로 어떻게 구현되어 있는 지와 동작 방법에 대해서 설명해주세요. (답변 부족)</summary>
      
    - 내부적으로 배열과 해시 함수를 통해 구현되어 있습니다.
    - 예를 들어, 각 데이터의 Key에 대한 해시 값을 계산 후 나머지 연산을 통해 나온 해당 위치에 저장합니다.
    - 즉 hashcode() % M 값으로 산출이 가능해 해당 인덱스에 Key와 Value를 저장합니다. 
    - 이를 통해 빠르게 검색이 가능하지만, 해시 충돌 가능성이 높습니다.
  </details>  
  <details>
    <summary>Hash Collision에 대해서 설명해주시고, 극복할 수 있는 방법에 대해서 설명해주세요. </summary>

    - 동일한 해시 값이 나오는 경우를 해시 충돌이라고 합니다.
    - 이는 연산 속도를 떨어뜨리기 때문에, 충돌을 최소화하는 것이 핵심이지만 해시 충돌 자체를 없애는 것은 거의 불가능에 가깝습니다.

    [해시 충돌 극복 방법]
    - 분리 연결법(Seperate Chaining)
      - 이는 해시 충돌이 일어나면 동일 버킷에 LinkedList로 저장하는 방법입니다.
      - 예를 들어, 특정 Key에 해시 함수로 나온 해시 값을 인덱스화해서 데이터를 저장해야 하는데, 이미 해당 위치에 저장된 데이터가 있다면,
        마치 LinkedList 구조처럼 동일한 버킷에 새로운 노드를 연결해 데이터를 저장합니다. 즉, 충돌이 계속 일어나면 노드가 계속 연결됩니다.
      - 하지만, 이 방식은 해시 함수로 해시 코드 값을 찾는데 O(1)의 시간복잡도가 걸리지만, Index 위치에서 해당 값을 찾기 위해 연결 리스트를
        하나씩 탐색해야 하기 때문에 노드 연결이 길어질수록 탐색 속도가 그만큼 늘어나게 되어 O(N) 시간복잡도를 가질 수 있게 됩니다.
        이 문제를 해결하기 위해 자바에서는 LinkedList 대신 Tree란 자료구조를 써서 시간복잡도를 줄입니다.
      - 자바에서의 분리 연결법
        - 자바에서는 해시 충돌이 일어날 경우 해당 방법을 사용해 대응해왔지만 Java 8부터는 데이터의 개수가 일정 이상일 때, LinkedList가 아닌 Tree를 사용합니다.
        - 그 이유는 LinkedList를 사용할 경우 해시 충돌이 많아질수록 성능은 떨어지게 되어있기 때문에 Tree로 변경해 성능을 O(n)에서 O(log n)으로 개선했습니다.
        - 정확하게는 LinkedList를 통해 연결된 노드의 숫자가 8을 넘어가는 경우 데이터 저장 방식 효율이 떨어지기 때문에, 이때부터 Red-Black Tree를 이용해 처리합니다.
        - 이때 일반 노드도 Tree Node로 변경됩니다. 또 굳이 Red-Black Tree를 사용하는 것은 균형이 무너지는 것을 막기위함입니다. 
        - 예를 들어, 일반 이진 트리는 균형이 무너져 최악의 경우 O(n)이 걸릴 수 있습니다.
      - 장점
        - 구현이 굉장히 단순하다.
        - LinkedList로 저장되어 테이블이 가득 차지 않는다.
        - Key의 삽입이나 삭제 횟수와 빈도를 알 수 없을 때 용이하다.
        - 해시 함수 및 적재율(Load Factor)에 영향을 덜 받는다.
      - 단점
        - 사용하지 않는 버킷이 생겨 불필요한 메모리 소모가 발생한다.
        - 연결 리스트를 사용해서 키를 저장하기 때문에 캐시 성능은 떨어진다.
        - 한 버킷에서 계속해서 저장된다면 체인이 길어져 최악의 경우 탐색 시, O(N)이 소모된다.
        - 연결 리스트 주소를 저장하기 위해 추가 메모리 공간이 요구된다.

    - 개방 주소법(Open Addressing)
      - 해시 충돌이 발생하면 다른 버킷에 데이터를 저장하는 방식입니다.
      - 즉, 해시 충돌이 일어난 키 값을 비어 있는 다른 주소를 찾아 저장하는 방법입니다.
      - 이는 모든 요소를 해시 테이블 자체에 저장하기 때문에 테이블의 크기는 키의 개수보다 반드시 크거나 같아야 합니다.
      - 장/단점
        - 연속된 공간에 데이터를 저장해 분리 연결법보다 캐시 효율이 높다. 단, 배열의 크기가 커질수록 L1, L2 캐시 적중률이 낮아져서 결국 안좋아진다.
      - 선형 탐사(Linear Probing)
        - 현재의 버킷 index로부터 고정폭만큼 씩 이동하여 차례대로 검색해 비어있는 버킷에 데이터 저장하는 방법입니다.
      - 제곱 탐사(Quadratic Probing)
        - 해시의 저장 순서 폭을 제곱으로 저장하는 방법입니다.
        - Ex) 첫 충돌 발생 시 1로 이동하고 그 다음부터는 2^2, 3^2 칸씩 검색합니다.
      - 이중 해싱(Double Hashing Probing)
        - 해시된 값을 한 번 더 해싱하여 해시의 규칙성을 없애는 방법입니다.
        - 다른 방법들보다 많은 연산을 필요로 합니다.
  </details>
</details> 

## JVM & Garbage Collector

<details>
  <summary><b>JVM이 정확히 무엇이고, 어떤 기능을 하는지 설명해 주세요.</b></summary>
  
  ---
  
  - JDK, JRE, JVM 차이점을 설명해주세요.
  - 자바 말고 다른 언어는 JVM 위에 올릴 수 없나요?
  - JVM 계열 언어를 일반적으로 컴파일해서 사용할 순 없나요?
  - VM을 사용함으로써 얻을 수 있는 장점과 단점에 대해 설명해 주세요.
  - JVM과 내부에서 실행되고 있는 프로그램은 부모 프로세스, 자식 프로세스 관계를 갖고 있다고 봐도 무방한가요?
  - JVM의 성능을 모니터링하고 분석해본 경험이 있나요? 있다면 설명해주세요.

  ---
</details>
<details>
  <summary><b>JVM 메모리 구조를 설명해주세요.</b></summary>
  
  ---
  
  - Stack과 Heap 메모리 차이점을 설명하세요.
  - Heap에 메모리를 할당하는 과정에 대해 설명하세요.
  - TLAB Thread-Local Allocation Buffer가 무엇인지 아시나요?
  - Permanent, Metaspace 영역 차이에 대해 설명해주세요.
  - Java 8 이후 Permanent 영역이 왜 사라졌을까요?

  ---
</details>
<details>
  <summary><b>자바는 컴파일 언어인가요? 인터프리터 언어인가요?</b></summary>
  
  ---
  
  - 컴파일 언어와 인터프리터 언어의 차이점은?
  - 자바 컴파일 과정을 설명해주세요.

  ---
</details>
<details>
  <summary><b>Java의 GC에 대해 설명해 주세요.</b></summary>

  ---

  - GC는 왜 필요할까요?
  - finalize() 를 수동으로 호출하는 것은 왜 문제가 될 수 있을까요?
  - 어떤 변수의 값이 null이 되었다면, 이 값은 GC가 될 가능성이 있을까요?
  - GC의 대상을 어떻게 판별할까요?
  - GC 동작과정을 설명해주세요.  
  
  ---
</details>
<details>
  <summary><b>STW (Stop-The-World)에 대해 설명하세요.</b></summary>
  
  ---

  
  ---
</details>
<details>
  <summary><b>`Parallel GC`, `G1 GC`, `ZGC`를 설명해주세요.</b></summary>
  
  ---

  
  ---
</details>

## Reference

- [https://mangkyu.tistory.com/](https://mangkyu.tistory.com/)
- [https://inpa.tistory.com/](https://inpa.tistory.com/)
- [https://gyoogle.dev/blog/](https://gyoogle.dev/blog/)
- [https://steady-coding.tistory.com/](https://steady-coding.tistory.com/)
- [변수는 어디에 저장되는가?](https://velog.io/@this-is-spear/%EA%B7%B8%EB%9E%98%EC%84%9C-static-%EB%B3%80%EC%88%98%EB%8A%94-%EC%96%B4%EB%94%94%EC%97%90-%EC%A0%80%EC%9E%A5%EB%90%98%EB%8A%94%EA%B0%80)
- [https://incheol-jung.gitbook.io/docs/q-and-a/java/static](https://incheol-jung.gitbook.io/docs/q-and-a/java/static)
- [자바 8부터 static이 Heap 영역에 저장된다.](https://jgrammer.tistory.com/entry/JAVA-Java8%EB%B6%80%ED%84%B0%EB%8A%94-static%EC%9D%B4-heap%EC%98%81%EC%97%AD%EC%97%90-%EC%A0%80%EC%9E%A5%EB%90%9C%EB%8B%A4)
- [쉬운코드 - List에 대해 아시나요?](https://www.youtube.com/watch?v=xvi-n11kym0)
- [해시와 해시충돌](https://cdragon.tistory.com/entry/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0-Hash%ED%95%B4%EC%8B%9C)
- [서채리 - HashTable vs HashMap](https://chaewsscode.tistory.com/183)
  
<!-- 

<details>
  <summary><b>인터페이스와 추상 클래스의 차이에 대해 설명해 주세요.</b></summary>

  - 왜 클래스는 단일 상속만 가능한데, 인터페이스는 2개 이상 구현이 가능할까요?
</details>
<details>
  <summary><b>Java 에서 Annotation 은 어떤 기능을 하나요?</b></summary>

  - 어노테이션은 자바 소스 코드에 메타데이터를 제공하는 방법입니다. 
  - 이는 코드의 의미를 설명하거나, 컴파일 시점이나 실행 시점에 특정 기능을 수행하도록 정보를 제공합니다. 
  - 예를 들어, @Override 어노테이션은 메서드가 상위 클래스의 메서드를 오버라이드한다는 것을 컴파일러에게 알려줍니다.
  - 예를 들어, @Autowired 어노테이션은 스프링 프레임워크에게 의존성 주입을 요청합니다.

  ---

  - 별 기능이 없는 것 같은데, 어떻게 Spring 에서는 Annotation 이 그렇게 많은 기능을 하는 걸까요?
  - Lombok의 @Data를 잘 사용하지 않는 이유는 무엇일까요?
</details>
-->
