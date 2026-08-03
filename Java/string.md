# String, StringBuffer, StringBuilder

## Q. String, StringBuffer, StringBuilder의 차이에 대해 설명해주세요.

### 답변
String은 자바의 대표적인 불변 객체로, 한번 생성되면 값을 바꿀 수 없고 문자열을 더하거나 수정할 때마다 새로운 객체가 생성됩니다.
반면 StringBuffer와 StringBuilder는 가변 객체로, 내부 버퍼를 직접 수정하기 때문에 새로운 객체를 만들지 않습니다.

그래서 문자열 수정이 잦은 로직에서 String을 쓰면 그만큼 객체가 계속 생성되고 버려져 메모리와 GC 비용이 늘어나는 반면, StringBuffer와 StringBuilder는 하나의 버퍼를 재사용해 이런 비용을 줄일 수 있습니다.

두 클래스의 차이는 동기화 여부인데, StringBuffer는 synchronized로 스레드 안전하지만 그만큼 느리고, StringBuilder는 동기화가 없어 단일 스레드에서 더 빠릅니다.
따라서 멀티스레드 환경이 아니라면 StringBuilder가 일반적으로 권장됩니다.

### 꼬리질문

**Q. String을 String Constant Pool에서 관리하는 이유는 무엇인가요?**

A. 같은 문자열을 매번 새로 만들면 메모리가 낭비되기 때문에, 이미 풀에 있는 값이면 기존 객체를 재사용합니다.

**Q. 반복문에서 문자열을 계속 더할 때 String을 쓰면 어떤 문제가 생기나요?**

A. 반복할 때마다 새로운 객체가 계속 생성되고 버려지기 때문에, 불필요한 GC 비용이 늘어나 성능이 저하됩니다.
