# Rest API & Restful 설계

> **참조문서**
> 

[[간단정리] REST, REST API, RESTful 특징](https://hahahoho5915.tistory.com/54) 

[RESTful API를 위한 6가지 원칙과 네이밍](https://prohannah.tistory.com/156)

[[Java] RESTful API 설계 방법 -1 : 이해하기](https://adjh54.tistory.com/150#3)

## ❓ REST API

- REST 기반으로 서비스 Api를 구현한 것.

✅ API란?

- Application Programming Interface : 애플리케이션 실행용 인터페이스(설계)
- 프로그램이나 라이브러리 실행을 하기 위한 인터페이스.
- 사용자가 요청한 데이터를 서버로 전달한 뒤

✅ REST란?

- Representational State Transfer
- 자원을 이름(표현)으로 구분하여 주고 받는 모든 행위를 의미.
- 자원(URI), 행위(HTTP Method), 표현(Represnetation)으로 구성.

> **❓HTTP 메서드**
> 
- GET : 조회
- POST : 데이터 추가
- DELETE : 데이터 삭제
- PUT : 데이터 수정(전쳬)
- PATCH : 데이터 수정(일부)

## ❗아래 특징을 준수한 api를 `RESTful` 한 API 라고 한다.

- Rest Api 특징
    - Servier-client 구조 : • 클라이언트, 서버 및 리소스로 구성되었으며 요청이 HTTP를 통해 관리되는 클라이언트-서버 아키텍처
    
    - Stateless : GET 요청 간에 클라이언트 정보가 저장되지 않으며, 각 요청이 분리되어 있고 서로 연결되어 있지 않음
    
    - Cacheable : 캐시 가능
    
    - Layered System : • 요청된 정보를 검색하는 데 관련된 서버(보안, 로드 밸런싱 등을 담당)의 각 유형을 클라이언트가 볼 수 없는 계층 구조로 체계화하는 계층화된 시스템.
    
    - Code-On-Demand : 요청을 받으면 서버에서 클라이언트로 실행 가능한 코드를 전송하여 클라이언트 기능을 확장할 수 있는 기능
    
    - Uniform Inteface : 정보가 표준 형식으로 전송되도록 하기 위한 구성 요소 간 통합 인터페이스.
    
- 설계 기본 및 규칙
    - 리소스를 표현하기 위해 명사를 사용해야 한다!
        
        Document : 단일개념 (파일 하나, 인스턴스 하나, 데이터베이스 row 1)
        
        Collection : 서버 내 관리되는 리소스의 디렉토리
        
        Store : 클라이언트 측에서 관리되는 자원 저장소
        
        Ex) `/files`
        
    - 규칙
        
        계층 관계 표현  시 `/` 사용하기
        
        ex) `http://project/memeber` 
        
        마지막 문자로 `/` 사용 금지!
        
        ex) `project/member/` → `project/member`
        
        가독성을 위해 `-` (하이픈) 사용하기
        
        ex) eurekaServer(X), eureka_server(X), eureka-server(O)
        
        소문자 및 명사로만 만든다.
        
        파일 확장자는 사용하면 안된다!