# CORS

## Q. CORS란 무엇인가요?

### 답변

CORS는 Cross-Origin Resource Sharing의 약자로, 서로 다른 Origin 간에 자원을 공유할 수 있도록 하는 정책입니다.

웹 개발을 하다 보면 프론트엔드 로컬 서버에서 API 서버로 요청을 보낼 때 자주 마주칩니다. 예를 들어 프론트엔드가 `localhost:3000`, 백엔드가 `localhost:8080`이면 포트가 다르기 때문에 서로 다른 Origin으로 판단됩니다.

브라우저는 보안상 다른 Origin의 응답을 기본적으로 제한합니다. 이때 서버가 `Access-Control-Allow-Origin` 같은 헤더를 통해 허용할 Origin을 알려주면, 브라우저가 해당 응답을 사용할 수 있게 됩니다.

또한 특정 요청에서는 브라우저가 실제 요청 전에 `OPTIONS` 메서드로 Preflight 요청을 보내, 이 요청을 서버가 허용하는지 먼저 확인합니다. 정리하면 CORS는 서버 간 통신 문제가 아니라 브라우저가 적용하는 보안 정책이고, 서버가 헤더로 허용 범위를 명시해야 해결됩니다.

### 키워드

- Same-Origin Policy
- Origin
- 프로토콜, 도메인, 포트
- Access-Control-Allow-Origin
- 브라우저 보안 정책
- Preflight
- OPTIONS

## Q. Same-Origin Policy와 CORS의 차이는 무엇인가요?

### 답변

Same-Origin Policy는 브라우저가 다른 Origin의 리소스 접근을 기본적으로 제한하는 보안 정책입니다.

CORS는 이 제한을 무조건 없애는 것이 아니라, 서버가 허용한 Origin에 대해서만 브라우저가 응답 사용을 허용하도록 하는 방식입니다.

## Q. Preflight 요청은 무엇인가요?

### 답변

Preflight는 브라우저가 실제 요청을 보내기 전에, 해당 요청을 보내도 안전한지 서버에 먼저 확인하는 요청입니다.

`OPTIONS` 메서드로 요청하며, 서버가 해당 Origin, Method, Header를 허용하는지 확인합니다. 서버가 허용한다고 응답하면 그때 실제 요청이 전송됩니다.

## Q. CORS 문제는 어떻게 해결하나요?

### 답변

CORS 문제는 보통 서버에서 허용할 Origin, Method, Header를 응답 헤더로 설정해서 해결합니다.

대표적으로 `Access-Control-Allow-Origin`, `Access-Control-Allow-Methods`, `Access-Control-Allow-Headers`를 사용합니다. 쿠키 같은 인증 정보를 포함한다면 `Access-Control-Allow-Credentials` 설정도 필요하며, 이 경우 `Access-Control-Allow-Origin: *`는 사용할 수 없습니다.
