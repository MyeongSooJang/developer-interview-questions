# JVM

## Q. JVM이란 무엇인가요?

### 답변

JVM은 Java Virtual Machine의 약자로, 자바 바이트코드를 실행하는 가상 머신입니다.

자바 코드는 컴파일되면 운영체제에 직접 종속되는 실행 파일이 아니라 `.class` 형태의 바이트코드가 됩니다. JVM은 이 바이트코드를 각 운영체제 환경에 맞게 실행합니다.

이 구조 덕분에 자바는 한 번 작성한 코드를 여러 환경에서 실행할 수 있는 Write Once, Run Anywhere라는 특징을 가집니다. 

또한 JVM은 메모리 관리, 스레드 관리, 가비지 컬렉션도 담당해서 개발자가 비즈니스 로직에 더 집중할 수 있게 해줍니다.

### 꼬리질문

#### Q. JDK, JRE, JVM의 차이는 무엇인가요?

JVM은 자바 바이트코드를 실행하는 가상 머신입니다. JRE는 JVM과 자바 프로그램 실행에 필요한 라이브러리를 포함한 실행 환경이고, JDK는 JRE에 컴파일러 같은 개발 도구까지 포함한 개발 키트입니다.

#### Q. 바이트코드란 무엇인가요?

바이트코드는 자바 소스 코드를 컴파일했을 때 생성되는 `.class` 파일 형태의 중간 코드입니다. 운영체제가 직접 실행하는 코드가 아니라 JVM이 읽고 실행하는 코드이기 때문에, JVM이 있는 환경이라면 같은 바이트코드를 실행할 수 있습니다.

#### Q. JVM의 메모리 구조는 어떻게 나뉘나요?

JVM 메모리는 대표적으로 Method Area, Heap, Stack으로 나눌 수 있습니다. Method Area에는 클래스 정보가 저장되고, Heap에는 객체가 저장되며, Stack에는 메서드 호출과 지역변수 정보가 저장됩니다.

#### Q. JVM의 구조는 어떻게 이루어져 있나요?

JVM은 크게 Class Loader, Execution Engine, Runtime Data Area로 구성됩니다. Class Loader는 `.class` 파일을 JVM으로 로딩하고, Execution Engine은 바이트코드를 해석하거나 JIT 컴파일해서 실행하며, Runtime Data Area는 실행 중 필요한 데이터를 저장하는 메모리 영역입니다.

#### Q. Java 프로그램은 어떤 방식으로 실행되나요?

1. Java 소스 코드는 `javac` 컴파일러를 통해 `.class` 바이트코드로 변환됩니다.
2. Class Loader가 클래스 파일을 JVM에 로딩합니다.
3. Execution Engine이 바이트코드를 해석하거나 JIT 컴파일해서 실행합니다.
4. 실행 중 필요한 데이터는 Runtime Data Area에 저장됩니다.

### 키워드

- Java Virtual Machine
- 바이트코드
- `.class`
- 플랫폼 독립성
- Write Once, Run Anywhere
- 인터프리터
- JIT 컴파일러
- 메모리 관리
- 스레드 관리
- Garbage Collection
