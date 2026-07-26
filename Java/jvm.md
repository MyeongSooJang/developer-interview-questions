# JVM

## Q. JVM이란 무엇인가요?

### 답변
JVM은 Java Virtual Machine으로, 자바 바이트코드를 각 운영체제 환경에 맞게 실행하는 가상 머신입니다.

자바 코드는 컴파일하면 `.class` 바이트코드가 되는데, JVM이 이를 인터프리터 또는 JIT 컴파일러로 실행합니다. 이 구조 덕분에 Write Once, Run Anywhere가 가능하며, 개발자는 OS에 종속되지 않고 코드를 작성할 수 있습니다.

실무에서는 JVM이 GC로 메모리를 자동 관리해주므로 명시적인 메모리 해제 없이도 개발이 가능합니다. 다만 Heap, Stack, Method Area로 나뉘는 메모리 구조와 GC 동작 방식을 이해하면 성능 이슈를 진단하는 데 도움이 됩니다.

### 꼬리질문
- JDK, JRE, JVM의 차이는 무엇인가요?
- 바이트코드란 무엇인가요?
- JVM의 메모리 구조는 어떻게 나뉘나요?
- JVM의 구성 요소(Class Loader, Execution Engine 등)는 무엇인가요?
- Java 프로그램은 어떤 순서로 실행되나요?
- GC(Garbage Collection)란 무엇인가요?
