# 개발자 면접 질문 리스트

Java 백엔드 개발자 취업 면접을 준비하기 위한 질문 저장소입니다.


## Categories

### Java

- [JVM이란 무엇인가요?](Java/jvm.md)
- [GC(Garbage Collection)란 무엇인가요?](Java/gc.md)
- [자바가 컴파일되는 과정을 설명해주세요.](Java/compile.md)
- [자바의 메모리 영역에는 뭐가 있는지 설명해주세요.](Java/memory.md)
- [OOP란 무엇인가요?](Java/oop.md)
- [인터페이스와 추상 클래스의 차이점에 대해 설명해주세요.](Java/interface-abstract.md)
- [오버로딩과 오버라이딩의 차이는 무엇인가요?](Java/overloading-overriding.md)
- [static 키워드에 대해 설명해주세요.](Java/static.md)
- [불변 객체란 무엇인지 설명해주세요.](Java/immutable.md)
- [String, StringBuffer, StringBuilder의 차이에 대해 설명해주세요.](Java/string.md)
- [Wrapper Class란 무엇이며, Boxing과 Unboxing은 무엇인지 설명해주세요.](Java/wrapper-class.md)
- [Java의 예외 종류에는 어떤 것들이 있고 무슨 차이가 있나요?](Java/exception.md)
- [equals()와 hashCode()를 같이 재정의하는 이유는 무엇인가요?](Java/equals-hashcode.md)

### Spring

### JPA

### DB

- [트랜잭션이란 무엇인가요?](DB/트랜잭션.md)

### 알고리즘 및 자료구조

### 기본 CS

- [OSI 7계층이란 무엇인가요?](기본-CS/OSI-7계층.md)
- [https://www.google.com 접속 시 일어나는 과정](기본-CS/구글-접속-과정.md)
- [TCP와 UDP의 차이점은 무엇인가요?](기본-CS/TCPUDP.MD)
- [CORS란 무엇인가요?](기본-CS/CORS.md)
- [Design Pattern - Singleton](기본-CS/singleton.md)
- [Design Pattern - Factory](기본-CS/factory.md)

## Question Template

```md
# 주제

## Q. 질문 내용

### 답변
[① 한 줄 정의 — 핵심 키워드를 자연스럽게 포함]

[② 이유/원리 — 왜 필요한지, 어떻게 동작하는지, 구체적 예시]

[③ 실무 연결 — 실제 사용 방식, 연관 개념, 트레이드오프]

### 꼬리질문
- 예상 꼬리질문 1
- 예상 꼬리질문 2
```

## Writing Rules

- 질문 제목은 `## Q.`로 시작합니다.
- 답변은 3단락 구조로 작성합니다: ① 정의 → ② 이유/원리 → ③ 실무 연결
- 핵심 기술 키워드(commit, rollback 등)는 별도 섹션 없이 ① 정의 단락에 자연스럽게 포함합니다.
- 답변 전체 길이는 소리내어 읽었을 때 30초~1분 분량을 목표로 합니다.
- 꼬리질문은 별도 `## Q.` 섹션 없이 리스트로 정리합니다.
- 실제로 찾아본 면접 질문이 있을 때만 관련 파일을 새로 만들고 정리합니다.
