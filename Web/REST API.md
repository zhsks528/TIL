---
title: "REST API"
date: "2020-09-09T21:08:22.441Z"
category: "cs"
emoji: ""
---

## REST API

### 1. REST의 정의

- **REpresentational State Transfer의 약자**로 전반적인 웹 어플리케이션에서 상호작용하는데 사용되는 웹 아키텍쳐 모델이다.
- 자원을 주고받는 **웹 상에서의 통신 체계에 있어서 범용적인 스타일을 규정한 아키텍쳐** 라고 할 수 있다.

### 2. API의 정의

- **Application Programming Interface의 약자**로 구글 맵 API, 카카오 비전 API 등 **기존에 있는 응용 프로그램을 통해서 데이터를 제공받거나 기능을 사용하고자 할 때 사용하는 인터페이스 및 규격** 을 말한다. 
- API는 프로그래밍 언어, 운영체제 등에서도 사용되는 범용적인 용어이다. 따라서, REST API라는 것은 REST 원칙을 적용하여 서비스 API를 설계한 것을 말하며 대부분의 서비스가 REST API를 제공한다.

### 3. REST의 구성요소

- **Resource (자원)**
  - 서버는 Unique한 ID를 가지는 Resource를 가지고 있으며, 클라이언트는 이러한 Resource에 요청을 보낸다.
  - 이러한 Resource는 **URI**에 해당한다.
- **Method (행위)**
  - **서버에 요청을 보내기 위한 방식**으로 GET, POST, PUT, DELETE가 있다.
  - CRUD 연산 중에서 처리를 위한 연산에 맞는 Method를 사용하여 서버에 요청을 보내야 한다.
- **Representation of Resource (표현)**
  - **클라이언트와 서버가 데이터를 주고받는 형태**로 json, xml, text, rss 등이 있다.
  - 최근에는 Key, Value를 활용하는 **json을 주로 사용**한다.

### 4. REST가 필요한 이유

1. **애플리케이션 분리 및 통합**
2. **다양한 클라이언트의 등장**
3. 최근의 서버 프로그램은 다양한 브라우저와 안드로이드폰, 아이폰과 같은 모바일 디바이스에서도 통신을 할 수 있어야 한다.

### 5. REST의 특징

#### 5-1. 균등한 인터페이스 (Uniform Interface)

- REST가 HTTP의 표준만 따른다면 어떠한 기술이던지 접목하여 사용할 수 있기 때문에 플랫폼이나 언어의 제약에 구애받지 않는다. 요즘은 REST API를 정의할 때 JSON(JavaScript Object Notation) 방식을 가장 많이 사용하지만 XML(eXtensible Markup Language)도 적용할 수 있다.

#### 5-2. 무상태성 (Stateless)

- 서버는 클라이언트의 상황을 고려하지 않고 API 요청에 대해서만 처리하기 때문에 이를 **"상태가 없다"** 라고 표현한다. 이렇게 되면 클라이언트를 고려하지 않아도 되기 때문에 구현이 간결해진다.

#### 5-3. 캐싱 가능 (Cacheable)

- **REST는 HTTP 표준을 기반으로 만들어졌기 때문에 HTTP의 특징인 캐싱을 사용**할 수 있다. REST API를 활용하여 `GET` 메소드를 `Last-Modified` 값과 함께 보낼 경우, 컨텐츠의 변화가 없을 때 캐시된 값을 사용하게 된다. 이렇게 되면 네트워크 응답시간 뿐만 아니라 API 서버에 요청을 발생시키지 않기 때문에 부담이 덜 하다는 장점 또한 가지게 된다.

#### 5-4. 자체 표현성 (Self-Descriptiveness)

- REST API의 자원명시 규칙 및 메소드는 그 자체로 의미를 지니기 때문에 어떠한 요청에 있어서 그 요청 자체로 어떤 것을 표현하는지 알아보기 쉽다. 물론 API를 규정한 각 서비스들이 문서를 제공하지만 이 특성에 따라서 요청하는 방식만으로 어떠한 의미인지 알 수 있어야 좋은 REST API라고 할 수 있다.

#### 5-5. 클라이언트-서버 구조 (Client-Server Architecture)

- **REST 서버가 API를 제공하는 방식이기 때문에 클라이언트에서 처리하는 부분과 독립적으로 동작**한다.
  - 서로간의 의존성이 줄어들고 클라이언트와 서버를 최대한 독립적으로 개발할 수 있도록 도와준다.

#### 5-6. 계층형 구조 (Layered System)

- 클라이언트는 계층형 구조가 불가능하지만 **REST 서버의 경우, 보안/로드 밸런싱/암호화 등을 추가할 수 있고 Proxy 및 게이트웨이 등의 중간매체를 사용**할 수 있다.

### 6. REST API의 정의

- REST 기반으로 서비스 API를 구현한 것이다.

### 7. REST API 중심 규칙

#### 7-1. URI는 정보의 자원을 표현해야 한다. (리소스명은 동사보다는 명사를 사용)

```
    GET /members/delete/1
```

- 위와 같은 방식은 REST를 제대로 적용하지 않은 URI이다. 
- **URI는 자원을 표현하는데 중점**을 두어야 한다. 
- delete와 같은 **행위에 대한 표현이 들어가서는 안된다**.

#### 7-2. 자원에 대한 행위는 HTTP Method(GET, POST, PUT, DELETE 등)로 표현

위의 잘못 된 URI를 HTTP Method를 통해 수정해 보면

```
    DELETE /members/1
```

으로 수정할 수 있다.
회원정보를 가져올 때는 GET, 회원 추가 시의 행위를 표현하고자 할 때는 POST METHOD를 사용하여 표현한다.

**회원정보를 가져오는 URI**

```
    GET /members/show/1     (x)
    GET /members/1          (o)
```

**회원을 추가할 때**

```
    GET /members/insert/2 (x)  - GET 메서드는 리소스 생성에 맞지 않는다.
    POST /members/2       (o)
```

### 8. REST API 설계시 주의할 점

#### 8-1. 슬래시 구분자(/)는 계층 관계를 나타내는 데 사용한다.

```
    http://restapi.example.com/houses/apartments
    http://restapi.example.com/animals/mammals/whales
```

#### 8-2. URI 마지막 문자로 슬래시(/)를 포함하지 않는다.

- URI에 포함되는 모든 글자는 리소스의 유일한 식별자로 사용되어야 하며 URI가 다르다는 것은 리소스가 다르다는 것이고, 역으로 리소스가 다르면 URI도 달라져야 한다. 

- **REST API는 분명한 URI를 만들어 통신을 해야 하기 때문에 혼동을 주지 않도록 URI 경로의 마지막에는 슬래시(/)를 사용하지 않는다.**

```
    http://restapi.example.com/houses/apartments/ (X)
    http://restapi.example.com/houses/apartments  (0)
```

#### 8-3. 하이픈(-)은 URI 가독성을 높이는데 사용

- URI를 쉽게 읽고 해석하기 위해, 불가피하게 긴 URI경로를 사용하게 된다면 하이픈을 사용해 **가독성을 높일 수 있다**.

#### 8-4. 밑줄(_)은 URI에 사용하지 않는다.

- 글꼴에 따라 다르긴 하지만 밑줄은 보기 어렵거나 밑줄 때문에 문자가 가려지기도 합니다. 이런 문제를 피하기 위해 밑줄 대신 하이픈(-)을 사용하는 것이 좋다.

#### 8-5. URI 경로에는 소문자가 적합하다.

- URI 경로에 대문자 사용은 피하도록 해야 한다. 
- -> 대소문자에 따라 다른 리소스로 인식하게 되기 때문이다. 
  - -> RFC 3986(URI 문법 형식)은 URI 스키마와 호스트를 제외하고는 대소문자를 구별하도록 규정하기 때문이다.

```
    RFC 3986 is the URI (Unified Resource Identifier) Syntax document
```

#### 8-6. 파일 확장자는 URI에 포함시키지 않는다.

```
    http://restapi.example.com/members/soccer/345/photo.jpg (X)
```

- REST API에서는 메시지 바디 내용의 포맷을 나타내기 위한 파일 확장자를 URI 안에 포함시키지 않는다.
- Accept header를 사용하도록 한다.

```
    GET / members/soccer/345/photo HTTP/1.1 Host: restapi.example.com Accept: image/jpg
```

### 9. 참고 자료

- [REST란? REST API란? RESTful 이란?](https://gmlwjd9405.github.io/2018/09/21/rest-and-restful.html)
- [REST API 제대로 알고 사용하기](https://meetup.toast.com/posts/92)
- [Rest API란?](https://mangkyu.tistory.com/46)
- [REST API](https://github.com/baeharam/Must-Know-About-Frontend/blob/master/Notes/network/rest-api.md)