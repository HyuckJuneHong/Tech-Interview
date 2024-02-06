<!--
<details>
  <summary><h3></h3></summary>

  ---

  <details>
    <summary></summary>
  </details>
</details> 
-->

<details>
  <summary><h3>1. 서블릿(Servlet)이란?</h3></summary>

  - 서블릿은 서버 측에서 실행되어 클라이언트의 요청을 처리하고 그 결과를 반환하는 Java 클래스입니다. 
  - 웹 서버(WS) 내에서 동작하며, 동적인 웹 페이지나 웹 애플리케이션을 생성하는데 사용됩니다. 

  ---
  
  <details>
    <summary>서블릿 생명주기에 대해 설명해주세요.</summary>

    - init():
      - 클라이언트의 요청이 들어오면 컨테이너는 해당 서블릿이 메모리에 올라와있는지 확인하고, 없을 경우 init() 메서드를 통해 메모리에 적재합니다.
      - 처음 한 번만 실행되고 서블릿의 모든 쓰레드에서 공통적으로 사용해야 한다면 오버라이딩해서 구현하면 됩니다.
    - service():
      - 클라이언트의 요청이 들어왔을 때, service() 메서드를 통해 요청에 대한 응답이 doGet()과 doPost()로 나뉘며 HttpServletRequest와 HttpServletResponse 객체가 제공됩니다.
      - 즉, 실질적으로 요청에 대한 처리를 수행하는 곳입니다.
    - destroy():
      - 컨테이너가 서블릿에 종료 요청을 하면 발생되는 메서드로, 서블릿의 처리가 모두 끝났을 때 발생합니다.
  </details>
  <details>
    <summary>서블릿 동작과정에 대해 설명해주세요.</summary>
    
    1. 사용자가 URL을 통해 요청을 보내면, 웹 서버는 이 요청을 서블릿 컨테이너에 전달합니다. 
    2. Servlet Container는 HttpServletRequest와 HttpServletResponse 객체를 생성합니다.
    3. 서블릿 컨테이너는 web.xml을 기반으로 요청을 처리할 서블릿을 찾아 실행합니다.
    4. 서블릿은 요청을 처리한 후 응답을 생성합니다.
    5. 서블릿 컨테이너는 이 응답을 웹 서버에 전달하고, 웹 서버는 이를 사용자에게 반환합니다.
  </details>  
  <details>
    <summary>서블릿의 경우 멀티 쓰레드 환경에서 어떻게 동작하는지 알려주세요.</summary>

    서블릿은 클라이언트의 요청이 들어올 때마다 새로운 쓰레드를 생성하여 처리합니다. 
    이는 서블릿 컨테이너가 관리하며, 이렇게 되면 각 쓰레드가 독립적으로 동작하기 때문에 한 사용자의 요청 처리가 다른 사용자의 요청 처리에 영향을 주지 않습니다. 
    이러한 특성으로 인해 서블릿은 멀티 쓰레드 환경에서 병렬 처리가 가능하며, 이를 통해 서버의 부하를 줄이고 처리 성능을 향상시킬 수 있습니다.
    하지만 멀티 쓰레드 환경에서는 공유 자원에 대한 동시 접근을 주의해야 합니다. 
    서블릿 인스턴스는 싱글톤으로 관리되기 때문에, 멤버 변수 등의 공유 자원을 쓰레드 간에 공유하게 됩니다. 
    따라서 동기화 문제를 방지하기 위해 서블릿의 멤버 변수를 사용하는 것은 추천하지 않습니다.
  </details>
</details>

<details>
  <summary><h3>2. 서블릿 컨테이너(Servlet Container)란?</h3></summary>

  - 톰캣처럼 서블릿을 지원하는 WAS로 서블릿의 생명주기를 관리하는 컴포넌트입니다. (WAS 내에 서블릿 컨테이너가 포함된다.)
  - 즉, 서블릿의 생성, 초기화, 호출, 소멸 등의 과정을 관리하며, 요청과 응답 객체를 생성하여 서블릿에 전달합니다.
  - 정리하면, 서블릿을 관리해주는 컨테이너로 클라이언트의 요청을 받아 응답할 수 있게 WS와 소켓으로 통신하는 역할을 합니다.

  ---

  <details>
    <summary>서블릿 컨테이너의 역할에 대해 설명해주세요.</summary>

    - 생명 주기 관리: 
      - 서블릿 컨테이너는 서블릿의 전체 생명 주기를 관리합니다. 
      - 이에는 서블릿의 로딩과 초기화, 요청 처리, 그리고 서블릿의 종료 등이 포함됩니다. 
      - 서블릿은 요청이 들어올 때마다 새로운 쓰레드를 생성하여 처리하므로, 이런 쓰레드 관리 역시 서블릿 컨테이너의 역할입니다.
    - 통신 지원: 
      - 서블릿 컨테이너는 HTTP 등의 프로토콜을 통해 클라이언트의 요청을 받아 서블릿에 전달하고, 서블릿의 처리 결과를 클라이언트에게 반환하는 역할을 합니다. 
      - 이를 통해 개발자는 복잡한 통신 관련 코드를 작성하지 않고도 웹 서비스를 개발할 수 있습니다.
    - 멀티 쓰레딩 지원: 
      - 서블릿 컨테이너는 클라이언트의 각 요청을 별도의 쓰레드에서 처리합니다. 
      - 이를 통해 여러 사용자의 요청을 동시에 처리할 수 있습니다.
    - 보안 관리: 
      - 서블릿 컨테이너는 웹 애플리케이션의 보안을 관리합니다. 
      - 이에는 인증, 권한 체크 등의 기능이 포함됩니다.
    - JSP 지원: 
        - 서블릿 컨테이너는 JSP 페이지를 서블릿으로 변환하고 실행하는 기능을 제공합니다. 
        - 이를 통해 동적인 웹 페이지를 쉽게 구현할 수 있습니다.
        
    따라서 서블릿 컨테이너는 웹 서버와 서블릿 사이에서 중추적인 역할을 수행하며, 
    서블릿의 생명 주기 관리, 통신 지원, 멀티 쓰레딩, 보안, JSP 지원 등의 기능을 제공합니다.
  </details>
</details> 

<details>
  <summary><h3>3. Tomcat이 정확히 어떤 역할을 하는 도구인가요?</h3></summary>

   - 웹 컨테이너(서블릿 컨테이너)와 웹 서버의 기능을 제공하는 웹 애플리케이션(WAS)입니다. 
   - 웹 서버로서의 역할로는 정적인 페이지를 사용자에게 제공하고, 서블릿 컨테이너로서의 역할로는 JSP(Java Server Pages)와 서블릿의 실행 환경을 제공합니다. 
   - 즉, 클라이언트의 요청을 받아 해당하는 동적 컨텐츠를 생성하고 응답을 반환하는 역할을 합니다.

  ---

  <details>
    <summary>톰캣 동작과정에 대해 설명해주세요.</summary>

    1) 클라이언트로부터 HTTP 요청이 들어오면, 톰캣은 Connector를 통해 이 요청을 받습니다. 
    2) Connector는 요청을 처리하기 위한 새로운 쓰레드를 생성하고, 요청 정보를 바탕으로 HttpRequest, HttpResponse 객체를 생성합니다. 
    3) 생성된 HttpRequest 객체는 Engine으로 전달되어 적절한 Context에 요청을 라우팅합니다. 
    4) Context는 요청 URI를 기반으로 적절한 Servlet을 찾습니다. 
    5) 찾아진 Servlet은 요청을 처리하고 그 결과를 HttpResponse 객체에 채워넣습니다. 
    6) 이렇게 생성된 HttpResponse 객체는 다시 Connector를 통해 클라이언트에게 전달됩니다.
  </details>
  <details>
    <summary>Spring 환경에서 tomcat 에 request 가 들어왔을 때 RequestMapping 에 도달하기까지 과정을 설명해주세요.</summary>

     1) 톰캣은 클라이언트의 요청을 받아 새로운 쓰레드를 생성하고, HttpServletRequest와 HttpServletResponse 객체를 생성합니다. 
     2) 스프링의 DispatcherServlet에 이 두 객체를 전달합니다. 
     3) DispatcherServlet은 HandlerMapping에게 이 요청을 처리할 Handler를 물어봅니다. 
     4) HandlerMapping은 요청의 URI, HTTP 메서드 등을 기준으로 @RequestMapping이 붙은 적절한 메서드를 찾아 반환합니다. 
     5) DispatcherServlet은 반환받은 Handler를 실행시킵니다. 이때 Handler는 대부분의 경우 @RequestMapping이 붙은 컨트롤러의 메서드가 됩니다.
  </details>
  <details>
    <summary>내장 톰캣과 외장 톰캣은 어떤식으로 구성되어 활용되나요?</summary>

    - 내장 톰캣: 
      - 스프링 부트 애플리케이션에 포함되어 있는 톰캣입니다. 
      - 애플리케이션이 시작될 때 톰캣 서버도 함께 시작되며, 애플리케이션이 종료될 때 톰캣 서버도 함께 종료됩니다. 
    - 외장 톰캣: 
      - 별도로 설치되어 있는 톰캣으로, WAR 파일 등을 배포하여 사용합니다. 
      - 서버의 시작과 종료는 별도로 관리되며, 여러 개의 애플리케이션을 한 서버에서 동작시킬 수 있습니다.
  </details>
  <details>
    <summary>내장 톰캣과 외장 톰캣의 차이점에 대해서 아는대로 설명해주세요.</summary>

    - 배포 방식:
      - 내장 톰캣: 애플리케이션과 함께 패키징되어 배포되며, JAR 파일 형태로 간편하게 배포할 수 있습니다. 
      - 외장 톰캣: WAR 파일 형태로 애플리케이션을 톰캣 서버에 배포해야 합니다. 
    - 운영 환경: 
      - 내장 톰캣: 애플리케이션마다 독립적인 서버를 가지므로 서로 영향을 주지 않습니다. 
      - 외장 톰캣: 여러 애플리케이션을 한 서버에서 운영하므로 서로 영향을 줄 수 있습니다. 
    - 관리: 
      - 내장 톰캣: 애플리케이션과 함께 시작되고 종료되므로 관리가 간편합니다. 
      - 외장 톰캣: 서버의 시작과 종료, 설정 등을 별도로 관리해야 합니다.
  </details>
  <details>
    <summary>혹시 Netty에 대해 들어보셨나요? 무엇인가요?</summary>
    
    Netty는 자바 네트워크 프로그래밍 라이브러리로, 비동기 이벤트 주도 네트워크 애플리케이션을 쉽게 개발할 수 있게 설계되었습니다.
    Netty를 사용하면 TCP/UDP 소켓 서버와 클라이언트, HTTP/HTTPS 서버와 클라이언트 등을 쉽게 구현할 수 있습니다. 
    또한, 네트워크 프로그래밍에서 발생할 수 있는 다양한 이슈들(예: 접속 수락, 메시지 읽기/쓰기, 에러 처리 등)을 효율적으로 처리할 수 있습니다.
  </details>
  <details>
    <summary>왜 Netty란 것을 사용할까요?</summary>

    1. 효율적인 리소스 관리: Netty는 비동기 이벤트 주도 모델을 사용하여 리소스를 효율적으로 관리하여 높은 동시 접속 처리 성능을 제공합니다.
    2. 쉬운 프로그래밍 모델: 복잡한 네트워크 프로그래밍을 보다 쉽게 구현할 수 있도록 도와줍니다.
    3. 높은 확장성: 다양한 프로토콜을 지원하며, 사용자가 직접 프로토콜을 구현할 수 있도록 지원합니다.
  </details>
</details>

<details>
  <summary><h3>4. MVC(Model-View-Controller)패턴이란?</h3></summary>
  
  MVC 패턴은 애플리케이션을 세 가지 역할로 구분한 개발 방법론입니다. 
  - Model: 애플리케이션의 정보, 데이터를 나타내며, 비즈니스 로직을 처리합니다.
  - View: 사용자에게 보여지는 화면입니다. Model이 처리한 데이터를 사용자에게 보여주는 역할을 합니다.
  - Controller: 사용자의 입력을 받아 Model에 작업을 지시하고, 그 결과를 View에 반영하여 사용자에게 전달하는 역할을 합니다.
  
  ---

  <details>
    <summary>Spring MVC란 무엇인가요?</summary>

    - Spring MVC는 Spring Framework의 일부로서, 웹 애플리케이션 제작을 위한 MVC 패턴 기반의 프레임워크입니다. 
    - Spring MVC는 웹 요청을 처리하고 응답을 생성하는 데 필요한 여러 기능을 제공합니다. 
    - 이에는 요청 매핑, 데이터 바인딩, 유효성 검사, 페이지 이동 등이 포함됩니다. 
  </details>
  <details>
    <summary>MVC1이랑 MVC2 패턴 차이에 대해 설명해주세요.</summary>

    Spring MVC1과 Spring MVC2는 웹 개발에 있어서 MVC 패턴을 구현하는 두 가지 방법입니다. 
    - Spring MVC1: 
      - 모든 요청과 응답이 JSP 페이지를 통해 처리되는 구조입니다. 
      - JSP 페이지가 Controller와 View의 역할을 모두 수행합니다. 
      - 단순한 웹 애플리케이션에 적합하나, JSP에 모든 정보가 담겨있기 때문에, 복잡한 애플리케이션에서는 코드 관리가 어렵습니다. 
    - Spring MVC2: 
      - 서블릿이 Controller 역할을, JSP가 View 역할을 수행하는 구조입니다. 
      - 즉, 요청을 하나의 컨트롤러(서블릿)가 먼저 받아서, 뷰와 모델의 중간 역할을 합니다.
      - 따라서, 컴포넌트 간 역할이 분리되어 있기 때문에, 유지보수 및 확장성이 좋아 대부분의 웹 애플리케이션은 MVC2 방식을 사용하고 있습니다.
      - 스프링에서는 디스패처 서블릿이 프론트 컨트롤러의 역할을 맡고 요청에 맞는 컨트롤러를 찾아 요청을 위임합니다.
  </details>
  <details>
    <summary>스프링 MVC 구조 흐름에 대해 과정대로 설명해보세요.</summary>

    1) 클라이언트의 요청이 들어오면, 디스패처 서블릿이 이를 가장 먼저 받습니다. 
    2) 디스패처 서블릿은 HandlerMapping에게 요청을 처리할 Handler를 물어봅니다. 
    3) HandlerMapping은 요청 URL, HTTP 메서드 등을 기준으로 적절한 Handler를 찾아 디스패처 서블릿에게 반환합니다. 
    4) 디스패처 서블릿은 반환받은 Handler를 실행시킵니다. 
    5) Handler(일반적으로 컨트롤러)는 비즈니스 로직을 처리하고 그 결과를 모델에 담아서 반환합니다. 
    6) 디스패처 서블릿은 Handler가 반환한 모델을 ViewResolver에 전달하고, 어떤 뷰를 사용할지 결정하게 합니다. 
    7) 디스패처 서블릿은 결정된 뷰를 사용해 클라이언트에게 응답을 보냅니다.

    이런 방식으로 스프링 MVC는 클라이언트의 요청을 적절한 컨트롤러에 연결하고, 그 결과를 클라이언트에게 반환하는 역할을 수행합니다.
  </details>
</details>

<details>
  <summary><h3>5. DispatcherServlet 이란?</h3></summary>
    
   - DispatcherServlet은 스프링 MVC의 핵심 컴포넌트로, 모든 클라이언트 요청을 최초로 받아들이는 프론트 컨트롤러 역할을 합니다. 
   - 요청에 따라 적절한 컨트롤러로 분배하고, 처리 결과를 사용자에게 반환하는 역할을 수행합니다.

  ---

  <details>
    <summary>Dispatcher Servlet의 동작 과정에 대해서 간단하게 설명해주세요.</summary>

    1. 클라이언트의 요청이 오면 디스패처 서블릿이 이를 가장 먼저 받습니다.
    2. 디스패처 서블릿은 HandlerMapping에게 요청을 처리할 Handler를 물어봅니다. 
    3. HandlerMapping은 요청 URL, HTTP 메서드 등을 기준으로 적절한 Handler를 찾아 디스패처 서블릿에게 반환합니다.
    4. 디스패처 서블릿은 반환받은 Handler를 실행시킵니다. 
    5. Handler(일반적으로 컨트롤러)는 비즈니스 로직을 처리하고 그 결과를 모델에 담아서 반환합니다.
    6. 디스패처 서블릿은 Handler가 반환한 모델을 ViewResolver에 전달하고, 어떤 뷰를 사용할지 결정하게 합니다.
    7. 디스패처 서블릿은 결정된 뷰를 사용해 클라이언트에게 응답을 보냅니다.
    
    이런 방식으로 디스패처 서블릿은 클라이언트의 요청을 적절한 컨트롤러에 연결하고, 그 결과를 클라이언트에게 반환하는 중심적인 역할을 수행합니다.
  </details>
  <details>
    <summary>Spring 에서 DispatcherServlet 은 왜 있어야 할까요?</summary>

    1. 프론트 컨트롤러 패턴 구현: 
      - 디스패처 서블릿은 디자인 패턴 중 하나인 프론트 컨트롤러 패턴을 구현합니다. 
      - 이 패턴은 모든 클라이언트 요청을 한 곳에서 받아 적절한 처리를 위임하는 역할을 합니다. 
      - 이를 통해 요청 처리 로직을 효율적으로 관리할 수 있게 됩니다.
    2. 요청 라우팅: 
      - 디스패처 서블릿은 클라이언트의 요청을 적절한 컨트롤러에게 전달하는 역할을 합니다. 
      - 이를 통해 요청에 따라 적절한 컨트롤러가 선택되고 실행됩니다.
    3. 뷰 렌더링: 
      - 컨트롤러의 처리 결과를 바탕으로 적절한 뷰를 선택하고 렌더링하는 역할을 합니다. 
      - 이를 통해 클라이언트에게 적절한 응답을 반환할 수 있습니다.
    4. 예외 처리: 
      - 디스패처 서블릿은 요청 처리 과정에서 발생하는 예외를 일관되게 처리합니다. 
      - 이를 통해 에러 페이지를 표시하거나 적절한 응답 코드를 반환하는 등의 예외 처리를 진행할 수 있습니다.

    따라서 DispatcherServlet은 스프링 MVC의 핵심적인 요소로서, 클라이언트의 요청 처리와 응답 반환, 예외 처리 등을 총괄하는 역할을 수행합니다. 
    이런 기능을 통해 개발자는 요청 처리 로직에 집중할 수 있게 됩니다.
    더 자세하게 설명하자면, web.xml에 맵핑되는 컨트롤러를 모두 등록해야 했는데, 현재는 디스패처 서블릿을 통해 모든 요청을 핸들링해주고 공통 작업을 처리해주면서 web.xml의 역할을 축소시켜 줬습니다.
  </details>
  <details>
    <summary>여러 요청이 들어온다고 가정할 때, DispatcherServlet은 한번에 여러 요청을 모두 받을 수 있나요?</summary>
    
    DispatcherServlet은 멀티스레드 환경에서 동작하므로 한 번에 여러 요청을 받아 처리할 수 있습니다. 
    각 요청은 별도의 스레드에서 처리되며, 이를 통해 동시에 여러 사용자의 요청을 처리할 수 있습니다.
  </details>  
  <details>
    <summary>수많은 @Controller 를 DispatcherServlet은 어떻게 구분 할까요?</summary>
    
    DispatcherServlet은 요청 URL을 분석하여 해당 요청을 처리할 @Controller를 결정합니다. 
    이는 스프링의 HandlerMapping이 수행하며, URL, HTTP 메서드, 요청 파라미터 등을 기반으로 적절한 컨트롤러를 찾습니다.
  </details>
  <details>
    <summary>handlerAdapter 는 무엇인가요? (답변 미작성)</summary>
  </details>
  <details>
    <summary>handlerMapping 는 무엇인가요? (답변 미작성)</summary>
  </details>
  <details>
    <summary>handlerInterceptor 는 무엇인가요? (답변 미작성)</summary>
  </details>
</details>

<details>
  <summary><h3>6. 필터(Filter)란?</h3></summary>

  - 필터는 클라이언트의 요청을 서블릿이나 JSP로 보내기 전에 특정 작업을 처리하거나, 서블릿이나 JSP의 응답을 클라이언트로 보내기 전에 특정 작업을 처리하는데 사용됩니다.
  - 예를 들어 인코딩, 로깅, 압축, 암호화 등의 작업을 필터를 통해 처리할 수 있습니다. 

  ---

  <details>
    <summary>Filter 메서드에 대해 설명해주세요.</summary>

    - init(FilterConfig): 
      - 필터의 초기화 작업을 수행하는 메서드입니다. 
      - 필터가 생성되고 난 후 한 번만 호출됩니다. 
      - 인자로 받는 FilterConfig 객체를 통해 필터의 초기화 파라미터를 얻을 수 있습니다.
    - doFilter(ServletRequest, ServletResponse, FilterChain):
      - 실제 필터의 로직을 수행하는 메서드입니다.
      - 클라이언트의 요청이 있을 때마다 호출됩니다.
      - 이 메서드에서는 요청이나 응답을 가공하거나, 특정 조건에 따라 요청의 처리를 건너뛰는 등의 작업을 할 수 있습니다.
      - 작업이 끝나면 FilterChain의 doFilter 메서드를 호출하여 다음 필터나 서블릿에게 요청과 응답을 전달합니다.
    - destroy():
      - 필터가 웹 컨테이너에서 제거되기 전에 호출되는 메서드입니다.
      - 이 메서드에서는 필터의 리소스를 해제하거나 종료에 필요한 작업을 수행합니다.
    
    이처럼 필터는 요청과 응답을 가공하거나 특정 작업을 수행하는 데 사용되며, 
    init, doFilter, destroy 세 가지 메서드를 통해 필터의 생명 주기를 관리합니다.    
  </details>
  <details>
    <summary>필터는 어떤 상황에 사용해야 할까요?</summary>

    필터는 주로 다음과 같은 상황에서 사용됩니다 :
    - 요청/응답 데이터의 변환 또는 가공: 예를 들어, 인코딩 변경, XSS 공격 방어 등 
    - 공통적인 요청 처리: 예를 들어, 사용자 인증, 세션 체크 등 
    - 로깅 및 감사 추적: 예를 들어, 요청 경로, 처리 시간, IP 주소 등의 정보를 로그로 남기는 경우 
  </details>
  <details>
    <summary>Spring에서 Interceptor와 Servlet Filter와 AOP 공통점, 차이점에 대해 설명해 주세요.</summary>

    공통점:
      - 모두 요청을 가로채어 특정 로직을 수행하는 역할을 합니다. 
    차이점: 
      - Servlet Filter: 서블릿 명세의 일부로서, 서블릿 실행 전후에 요청과 응답을 변환하는 역할을 담당합니다. 
      - Interceptor: 스프링 프레임워크에서 제공하는 기능으로서, DispatcherServlet이 컨트롤러를 호출하기 전후로 특정 작업을 수행할 수 있습니다. 
      - AOP(Aspect Oriented Programming): 관점 지향 프로그래밍으로, 횡단 관심사(cross-cutting concerns)를 분리하여 모듈화하는 프로그래밍 패러다임입니다.
  </details>  
  <details>
    <summary>Spring에서 Interceptor와 Servlet Filter 차이점에 대해 설명해 주세요.</summary>

    1. 작동 시점 
      - 필터: 스프링의 디스패처 서블릿이 작동하기 전에 요청을 가로챕니다. 
             따라서 필터는 스프링의 컨텍스트 외부에서 작동하며, 스프링과 관련이 없는 웹 리소스에 대해서도 작동합니다. 
      - 인터셉터: 스프링의 디스패처 서블릿이 컨트롤러를 호출하기 전과 후에 요청을 가로챕니다. 
                따라서 인터셉터는 스프링의 컨텍스트 내부에서 작동하며, 스프링 MVC의 컨트롤러에 대해서만 작동합니다. 
    2. 접근 가능한 객체
      - 필터: HttpServletRequest와 HttpServletResponse 객체에만 접근할 수 있습니다. 
      - 인터셉터: HttpServletRequest와 HttpServletResponse 뿐만 아니라, 컨트롤러와 뷰에 대한 추가적인 정보를 담고 있는 Handler 객체에 접근할 수 있습니다. 
                이를 통해 특정 컨트롤러에 대한 요청인지를 판단하거나, 컨트롤러의 실행 여부를 결정하는 등의 로직을 구현할 수 있습니다. 
    3. 사용 목적
      - 필터: 인코딩, CORS 설정, 로깅 등의 공통적인 웹 처리를 위해 사용됩니다. 
      - 인터셉터: 인증, 권한 체크, 세션 체크 등의 스프링 MVC와 관련된 처리를 위해 사용됩니다.
      
    정리하자면, 요구 사항에 따라 필터와 인터셉터를 적절히 사용하면 됩니다. 
    필터는 보다 일반적인 웹 처리를 위한 것이며, 인터셉터는 스프링 MVC의 특정 컨트롤러에 대한 요청을 처리하는 데 더 적합합니다.
  </details>
  <details>
    <summary>필터와 인터셉터 차이만 보면, 인터셉터만 쓰는게 나아보이는데, 아닌가요?</summary>

    아니라고 생각합니다. 필터와 인터셉터는 각각의 용도에 따라 선택적으로 사용됩니다. 
    필터는 서블릿 수준에서 작동하므로 스프링 컨텍스트를 벗어난 모든 요청에 대해 적용할 수 있습니다. 
    반면에 인터셉터는 스프링의 디스패처 서블릿이 컨트롤러를 호출하기 전후에 작동하기 때문에 스프링 MVC의 컨트롤러에만 적용할 수 있습니다.
    따라서 요구 사항에 따라 적절한 것을 선택하여 사용하면 됩니다.
  </details>
  <details>
    <summary>필터에서 사용되는 Request와 서블릿에서 사용되는 Request가 어떤 점이 다른지? 2개의 Request에 대한 차이를 설명해주세요.</summary>

    필터와 서블릿에서 사용되는 Request는 동일한 HttpServletRequest 객체를 참조하지만, 다른 점은 다음과 같습니다.

    필터:
      - HttpServletRequest 객체를 변경하거나 추가적인 속성을 부여하는 등의 작업을 할 수 있습니다.
      - 즉, 클라이언트의 요청을 서블릿이나 JSP로 보내기 전에 특정 작업을 처리하거나, 서블릿이나 JSP의 응답을 클라이언트로 보내기 전에 특정 작업을 처리하는데 사용됩니다. 
      - 이 과정에서 필터는 HttpServletRequest를 가공하여 변경된 요청 객체나 새로운 요청 객체를 생성할 수 있습니다. 
      - 이렇게 변경된 HttpServletRequest는 후속 필터나 최종 목적지인 서블릿에 전달됩니다.
    서블릿:
      - 서블릿에서 사용되는 HttpServletRequest는 필터를 거쳐 가공된 최종적인 요청 객체입니다. 
      - 이 객체를 통해 클라이언트의 요청 정보를 읽고 필요한 로직을 처리합니다.
  </details>
  <details>
    <summary>필터를 사용해본 경험이 있으면 말씀해주시고, 필터에서 예외 처리를 해본 경험이 있는지 있다면 어떻게 할 수 있는지 말씀해주세요.</summary>

    스프링 시큐리티 어쩌구... 저쩌구.. 필터.. 어쩌구 저쩌구.. 사용자 로그인 상태를 체크 어쩌구.. 쿠키 체크.. 저쩌구.. 또한 헤더에 담겨 함께 넘어온 JWT 토큰 유효화 검증 어쩌구.. OncePerFilter 저쩌구..
  </details>
  <details>
    <summary>Spring에서 Interceptor를 사용해본 경험이 있나요? (답변 미작성)</summary>
  </details>
</details>

<details>
  <summary><h3>7. 스프링(Spring)이란?</h3></summary>

  - 스프링은 자바 플랫폼을 위한 오픈 소스 애플리케이션 프레임워크입니다. 
  - 엔터프라이즈 수준의 애플리케이션을 구축하는 데 필요한 모든 기능을 종합적으로 제공하며, 특히 엔터프라이즈 애플리케이션 개발의 복잡함을 줄이고 개발자가 비즈니스 로직에 집중할 수 있도록 지원합니다.
  - 스프링의 핵심 기능 중 하나는 제어 역전(Inversion of Control, IoC)입니다. IoC는 객체의 생성과 생명주기 관리를 개발자가 아닌 프레임워크가 담당하며, 이를 통해 개발자는 비즈니스 로직 구현에만 집중할 수 있습니다.

  ---

  <details>
    <summary>Spring과 Spring Boot의 차이점이 뭔가요?</summary>

    스프링 부트는 스프링 프레임워크를 기반으로 하되, 스프링보다 애플리케이션을 더 쉽게 설정하고 실행할 수 있게하여 비즈니스 로직에 더 집중할 수 있도록 도와주는 도구입니다.
    
    스프링 부트의 주요 특징은 다음과 같습니다:
      - 자동 설정(Auto Configuration): 스프링 부트는 애플리케이션에 필요한 라이브러리와 설정을 자동으로 제공합니다.
      - 내장 서버 지원: Tomcat, Jetty 등의 웹 서버를 내장하고 있어 별도의 서버 설치 없이 웹 애플리케이션을 실행할 수 있습니다.
      - 독립적인 실행 가능: JAR 파일 하나로 애플리케이션을 실행할 수 있습니다.

    따라서, 스프링 부트는 스프링 프레임워크의 기능을 그대로 활용하면서, 복잡한 설정 없이도 빠르게 애플리케이션을 구축하고 실행할 수 있는 환경을 제공합니다.
  </details>
  <details>
    <summary>Spring, Spring Boot, Spring MVC의 차이점에 대해 알려주세요.</summary>

    - Spring: 
      - Spring은 엔터프라이즈 급의 애플리케이션을 쉽게 개발할 수 있도록 지원하는 프레임워크입니다. 
      - 제어 역전(IoC), 의존성 주입(DI), AOP 등 다양한 기능을 제공하며, 이를 통해 개발자는 비즈니스 로직에 집중할 수 있습니다.
      - 하지만, 설정이 복잡하고, 외장 웹서버를 이용해야 합니다.
    - Spring MVC: 
      - Spring MVC는 Spring Framework의 일부로, 웹 애플리케이션을 개발하기 위한 MVC 패턴 기반의 프레임워크입니다. 
      - 클라이언트의 요청을 처리하고 응답을 반환하는 데 필요한 컨트롤러, 뷰, 모델 등을 제공합니다. 
      - 즉, 디스패처 서블릿, ModelAndView, ViewResolver와 같은 개념으로 웹 애플리케이션을 개발할 수 있도록 도와주는 프레임워크입니다.
      - 단, XML 파일에 직접 모든 것을 설정해줘야 합니다.
    - Spring Boot: 
      - Spring Boot는 Spring 기반의 애플리케이션을 빠르게 만들고 실행할 수 있도록 지원하는 도구입니다. 
      - Spring Boot는 자동 설정, 내장 서버, 독립적으로 실행 가능한 JAR 배포 등을 통해 개발자의 생산성을 크게 향상시킵니다.

    따라서, Spring은 애플리케이션 개발의 기본 틀을 제공하며, 
    Spring MVC는 웹 애플리케이션 개발을 위한 구조를 제공하고, 
    Spring Boot는 Spring 애플리케이션 개발을 쉽고 빠르게 할 수 있도록 지원하는 도구입니다.
  </details>
  <details>
    <summary>본인이 생각할 때 스프링과 스프링부트는 각각 어느때 사용할 것 같은지 설명해주세요.</summary>

    1. 스프링 사용 시기: 
      - 세밀한 설정이 필요한 경우: 
        - 스프링은 개발자가 직접 설정을 통해 원하는 대로 커스터마이징할 수 있습니다. 
        - 따라서 세밀한 설정이 필요하거나, 특정 라이브러리 버전을 사용해야 하는 등의 상황에서는 스프링을 사용하는 것이 좋습니다. 
      - 레거시 프로젝트 유지 및 보수: 
        - 이미 스프링을 기반으로 구축된 레거시 프로젝트를 유지하고 보수하는 경우에도 스프링을 계속 사용하는 것이 좋습니다. 
    2. 스프링 부트 사용 시기:
      - 빠른 개발이 필요한 경우: 
        - 스프링 부트는 자동 설정, 내장 서버, 독립적으로 실행 가능한 JAR 배포 등을 통해 빠르게 애플리케이션을 개발하고 배포할 수 있습니다. 
        - 따라서 개발 시간을 최소화하거나 프로토타입을 빠르게 만들어야 하는 경우에 스프링 부트를 사용하는 것이 좋습니다. 
      - 마이크로서비스 아키텍처: 
        - 스프링 부트는 독립적으로 실행 가능한 애플리케이션을 만들기 쉬워 마이크로서비스 아키텍처를 구축하는 데 적합합니다.

    결국 스프링과 스프링 부트 중 어떤 것을 선택할지는 개발 상황, 요구 사항, 기술 스택 등에 따라 달라집니다. 
    두 프레임워크 모두 강력하고 유연성이 높으므로 상황에 맞게 적절히 선택하면 됩니다.
  </details>
  <details>
    <summary>스프링의 전체 동작 과정에 대해 설명해주세요. (답변 미작성)</summary>
  </details>
</details>

<details>
  <summary><h3>8. IoC와 DI에 대해 설명해 주세요.</h3></summary>

  ---

  <details>
    <summary>후보 없이 특정 기능을 하는 클래스가 딱 1개라면, 구체 클래스를 사용해도 되지 않을까요? 근데, 왜 Spring에선 Bean을 사용 할까요?</summary>
  </details>
  <details>
    <summary>Spring의 Bean 생성 주기에 대해 설명해 주세요.</summary>
  </details>
  <details>
    <summary>Bean Scope 에 대해서 아시나요? 안다면, 해당 Scope들을 설명해주세요.</summary>
  </details>
  <details>
    <summary>default scope 가 어떤 scope인지 이유와 함께 설명하세요.</summary>
  </details>
  <details>
    <summary>prototype scope 는 어떨 때 사용하는 지 아시나요?</summary>
  </details>
  <details>
    <summary>인스턴스를 새로 만들지 않고 재사용하는 것은 어떤 장점이 있나요?</summary>
  </details>
  <details>
    <summary>생성자 주입 방식을 사용하는 이유가 있나요?</summary>
  </details>
  <details>
    <summary>스프링 컨테이너란 무엇인가요?</summary>
  </details>
  <details>
    <summary>VO, DTO 차이에 대해 설명하세요.</summary>
  </details>
  <details>
    <summary>엔티티, VO 차이에 대해 설명하세요.</summary>
  </details>
  <details>
    <summary>DAO(Data Access Object)란 무엇인가요?</summary>
  </details>
  <details>
    <summary>어노테이션이란 무엇이란 무엇인가요?</summary>
  </details>
  <details>
    <summary>빈 혹은 컴포넌트 등록을 위한 각 어노테이션을 설명해주세요.</summary>
  </details>
  <details>
    <summary>Spring에서 @Controller 와 @RestController 은 어떤 차이가 있나요?</summary>
  </details>
  <details>
    <summary>그렇다면, @Controller 로 작성했을 땐 Rest 방식인 String JSON 으로 반환하지 못하나요?</summary>
  </details>
  <details>
    <summary>빈과 컴포넌트 차이에 대해 설명해주세요.</summary>
  </details>
  <details>
    <summary>컴포넌트는 메서드 단에서 사용못하나요?</summary>
  </details>
  <details>
    <summary>BeanFactory vs ApplicationContext 차이에 대해 설명해주세요.</summary>
  </details>
</details>

<details>
  <summary><h3>9. AOP(Aspect Oriented Programming)에 대해 설명해 주세요.</h3></summary>

  ---

  <details>
    <summary>AOP 동작원리에 대해 설명해보세요.</summary>
  </details>
  <details>
    <summary>AOP 용어들을 설명해보세요. (Advice, Joinpoint, Pointcut, Weaving, Aspect)</summary>
  </details>
  <details>
    <summary>@Aspect는 어떻게 동작하나요?</summary>
  </details>
  <details>
    <summary>AspectJ 란 무엇인가요?</summary>
  </details>
  <details>
    <summary>AOP와 필터, 인터셉터의 차이점에 대해 자세하게 설명해보세요.</summary>
  </details>
  <details>
    <summary>AOP 를 실제로 사용해 본 경험이 있나요?</summary>
  </details>
  <details>
    <summary>AOP 를 동작시키기 위해 어떤 조건 혹은 어떤 코드를 구성을 해야 AOP 가 정상적으로 동작하는지 아시나요?</summary>
  </details>
  <details>
    <summary>AOP 적용할 수 있는 포인트가 메서드라고 했을 때 메서드의 시작과 끝에 AOP 를 걸 수가 있습니다. 이때, 메서드를 호출하는 과정에서 메서드가 다른 외부에서의 호출이거나 동일한 클래스 내부에서의 호출이 될 수도 있습니다. 이런 경우에 모두 AOP가 동작하나요? 근거와 함께 설명해주세요.</summary>
  </details>
</details>

<details>
  <summary><h3>10. 프록시가 무엇인지 아시나요?</h3></summary>

  ---

  <details>
    <summary>프록시 패턴이란 무엇인가요?</summary>
  </details>
  <details>
    <summary>프록시 객체란 무엇인가요?</summary>
  </details>
  <details>
    <summary>프록시 서버란 무엇인가요?</summary>
  </details>
  <details>
    <summary>리버스 프록시에 대해 설명해주세요.</summary>
  </details>
  <details>
    <summary>포워드 프록시에 대해 설명해주세요.</summary>
  </details>
  <details>
    <summary>JDK Dynamic Proxy에 대해 설명해주세요.</summary>
  </details>
  <details>
    <summary>CGLIB에 대해 설명해주세요.</summary>
  </details>
</details>  

<details>
  <summary><h3>11. JPA와 같은 ORM을 사용하는 이유가 무엇인가요?</h3></summary>

  ---
  
  - 영속성은 어떤 기능을 하나요? 이게 진짜 성능 향상에 큰 도움이 되나요?
  - N + 1 문제에 대해 설명해 주세요.
</details>

<details>
  <summary><h3>12. @Transactional 은 어떤 기능을 하나요?</h3></summary>

  ---
  
  - @Transactional(readonly=true) 는 어떤 기능인가요? 이게 도움이 되나요?
  - 그런데, 읽기에 트랜잭션을 걸 필요가 있나요? @Transactional을 안 붙이면 되는거 아닐까요?
</details>