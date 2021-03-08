#TIL/network
# REST API 에 대하여
## REST API 란?
- **RE**presentational **S**tate **T**ransfer **A**pplication **P**rogramming **I**nterface 의 약자이다.
- 인터넷 상의 시스템 간의 상호 운용성(interoperability)을 제공하는 방법중 하나
- 시스템 제각각의 독립적 진화를 보장하기위한 방법
- HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource)을 명시하고, HTTP Method(POST, GET, PUT, DELETE)를 통해 해당 자원에 대한 CRUD Operation을 적용하는 것을 의미한다.

## REST 아키텍처 스타일
- Client-Server
- Stateless
- Cache
- **Uniform Interface**
- Layered System
- Code-On-Demand (optional)

REST 아키텍처 스타일 중 Uniform Interface 에 대한 스타일을 따르지 않는 API 가 대다수이고, 그런 API 는 REST API 라고 부를 수 없다.

### Uniform Interface
- Identification of resources
- manipulation of resources through representations
- **self-descriptive messages**
- **hypermedia as the engine of application state (HATEOAS)**

Uniform Interface 중 self-descriptive messages, HATEOAS 가 지켜지지 않는 경우가 대다수이다.

#### self-descriptive messages
- 메세지 스스로에 대한 설명이 가능해야한다.
- 서버가 변해서 메시지가 변해도 클라이언트는 그 메시지를 보고 해석이
가능하다.
- 확장이 가능한 커뮤니케이션

#### HATEOAS
- 하이퍼 미디어 (링크) 를 통하여 상태변화가 가능해야한다.
- 링크 정보를 versioning 없이 동적으로 바꿀 수 있다.

#### self-descriptive messages 해결 방법
1. 미디어 타입을 정의하고 IANA에 등록하고 그 미디어 타입을 리소스 리턴할 때
Content-Type으로 사용한다.
2. Profile 링크 헤더를 추가한다.
— 브라우저들이 헤더에 링크를 추가하는 스펙을 잘 지원하지 않는 경우가 많다.
— 대안으로 HAL 의 링크 데이터에 profile 링크를 추가한다.

#### HATEOAS
1. 데이터에 링크를 제공한다.
— 링크를 어떻게 정의할 것인가? HAL
2. 링크 헤더나 location 을 제공한다. 