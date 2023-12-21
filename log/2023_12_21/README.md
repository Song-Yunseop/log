# 프로젝트 구축
## properties와 yml의 차이점
```
properties와 yml의 대표적인 차이는 내부 구조가 있다. properties의 경우엔 각 줄마다 key=value의 형태로 이루어져 있지만, yml의 경우엔 들여쓰기로 구분되는 계층 구조 및 key: value의 형태로 이루어져 있다.

결론적으로는 어떤 것을 사용해도 아무 문제가 없고, 기본적인 구조는 비슷하기 때문에 편한 것을 사용하면 되겠다. 개인적으로는 yml을 사용하는 것이 더 구조를 파악하기 쉽고, 중복되는 코드가 줄어들기 때문에 yml을 사용하는 것이 더 좋다고 생각한다.

주의할 점은 properties와 yml을 함께 사용하면 properties 파일이 우선순위가 높아 yml 파일에서 설정한 내용이 덮어씌워질 수 있다는 점이다. 따라서 되도록이면 둘 중 한쪽만 사용하는 것이 권장된다.
```

## 의존성
```
Oracle Driver
JDBC API
	JDBC (Java Database Connectivity)는 자바에서 데이터베이스에 접속할 수 있는 	API(응용 프로그래밍 인터페이스)입니다.
	JDBC는 데이터베이스와의 통신을 가능하게 하며, 데이터베이스에서 데이터를 가져오거나 변경할 수 	있는 기능을 제공한다.
	즉 JDBC를 사용하면  Java 애플리케이션에서 데이터베이스에 접근하여 데이터를 검색, 삽입, 	갱신, 삭제할 수 있다.
	
Lombok
	Lombok이란 Java의 라이브러리로 반복되는 메소드를 Annotation을 사용해서 자동으로 	작성해주는 라이브러리다. 보통 DTO나 Model, Entity의 경우 여러 속성이 존재하고 이들이 	가지는 프로퍼티에 대해서 Getter나 Setter, 생성자 등을 매번 작성해줘야 하는 경우가 있다. 	이러한 부분을 자동으로 만들어주는 라이브러리다. Lombok을 이용해서 작성한 코드는 컴파일 	과정에서 Annotation을 이용해서 코드를 생성하고 .class에 자동 컴파일 된다.

MYBatis Framework
	객체지향 언어인 자바의 관계형 데이터 베이스 프로그래밍을 좀더 쉽게 할수 있게 도와주는 개발 	프레임워크이다.자바는 jdbc api 를 제공해주지만, 이런 JDBC를 이용하면 1개 클래스에 	반복된 코드가 존재, 한 파일에 java언어와 sql언어가 있어서 재사용성 등이 안좋아지는 단점이 	있다.Mybatis는 jdbc의 이러한 단점들을 개선했으며, 개발자가 작성한 SQL 명령어와 자바 	객체를 매핑해주는 기능을 제공하며, 기존에 사용하던 SQL 명령어를 재사용한다.

Spring Boot DevTools
	Spring Boot Application을 개발하고 디버깅을 하는데 도움이 되는 도구 모음을 	의미합니다.
	
Spring Web
	멀티 파트 파일 업로드, 서블릿 리스너 등 웹 지향 통합 기능을 제공한다. HTTP클라이언트와 	Spring의 원격 지원을 위한 웹 관련 부분을 제공합니다.
	Spring Web Services

Thymeleaf
	타임리프는 자바 라이브러리이며, 텍스트, HTML, XML, Javascript, CSS 그리고 	텍스트를 생성할 수 있는 템플릿 엔진이다.
	스프링 MVC와의 통합 모듈을 제공하며, 애플리케이션에서 JSP로 만든 기능들을 완전히 대체할 수 	있다.
	Spring Boot에서는 JSP가 아닌 Thymeleaf 사용을 권장하고 있다.
```