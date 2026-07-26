# CORS

## Q. CORS란 무엇인가요?

### 답변
CORS는 Cross-Origin Resource Sharing으로, 브라우저의 Same-Origin Policy가 차단하는 다른 Origin 간 요청을 서버 측 헤더로 허용하는 메커니즘입니다.

브라우저는 보안상 프로토콜, 도메인, 포트 중 하나라도 다르면 다른 Origin으로 판단해 응답을 차단합니다. 예를 들어 `localhost:3000`에서 `localhost:8080`으로 요청 시 포트가 달라 차단됩니다. 서버가 `Access-Control-Allow-Origin` 헤더로 허용 Origin을 명시하면 브라우저가 응답을 허용합니다.

중요한 점은 CORS는 서버 간 통신 문제가 아니라 브라우저가 적용하는 보안 정책이라는 것입니다. 또한 PUT, DELETE나 커스텀 헤더를 포함한 요청은 실제 요청 전에 `OPTIONS`로 Preflight 요청을 먼저 보내 서버가 허용하는지 확인합니다. Spring에서는 `@CrossOrigin`이나 `WebMvcConfigurer`로 설정합니다.

### 꼬리질문
- Same-Origin Policy란 무엇인가요?
- Preflight 요청은 왜 필요한가요?
- CORS 문제는 어떻게 해결하나요?
- 쿠키를 포함한 CORS 요청에서 주의할 점은 무엇인가요?
