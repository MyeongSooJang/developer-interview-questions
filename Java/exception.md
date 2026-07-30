# Java 예외 종류

## Q. Java의 예외 종류에는 어떤 것들이 있고 무슨 차이가 있나요?

### 답변
자바의 예외는 컴파일러가 처리를 강제하는 체크 예외와, 강제하지 않는 언체크 예외로 나뉩니다.
체크 예외는 RuntimeException을 제외한 Exception의 하위 타입이고, 언체크 예외는 RuntimeException의 하위 타입입니다.

체크 예외는 try-catch나 throws로 처리하지 않으면 컴파일이 안 되기 때문에, IOException처럼 미리 예측 가능한 상황에서 주로 사용됩니다.
반면 언체크 예외는 처리를 강제하지 않고 실행 중에 발생하는데, NullPointerException처럼 코드 실수로 런타임에 터지는 경우가 많습니다.

여기에 더해 Throwable에는 Error도 있는데, StackOverflowError처럼 코드로 복구하기 어려운 시스템 레벨 문제라서 예외 처리 대상으로 보지 않습니다.
그래서 저희가 다루는 예외 처리는 대부분 Exception 영역에 해당합니다.

### 꼬리질문

**Q. Checked Exception과 Unchecked Exception의 차이는 무엇인가요?**

A. Checked Exception은 반드시 try-catch나 throws로 처리해야 컴파일이 되는 예외이고, Unchecked Exception은 그런 처리를 강제하지 않고 런타임에 발생하는 예외입니다.

**Q. Error와 Exception의 차이는 무엇인가요?**

A. Error는 StackOverflowError나 OutOfMemoryError처럼 개발자가 해결하기 어려운 문제이고, Exception은 코드 수정을 통해 해결할 수 있는 문제입니다.
