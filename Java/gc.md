# GC (Garbage Collection)

## Q. GC(Garbage Collection)란 무엇인가요?

### 답변
GC는 JVM이 Heap 메모리에서 더 이상 참조되지 않는 객체를 자동으로 제거하는 메커니즘입니다.

GC가 필요한 이유는 개발자가 직접 메모리를 해제하지 않으면 메모리 누수가 발생하기 때문입니다. JVM은 "대부분의 객체는 금방 죽는다"는 Generational Hypothesis에 기반해 Heap을 Young Generation과 Old Generation으로 나눕니다. 새 객체는 Young의 Eden 영역에 할당되고, Minor GC에서 살아남은 객체는 Survivor를 거쳐 Old Generation으로 승격됩니다.

GC의 핵심 문제는 STW(Stop-The-World)입니다. GC 실행 중에는 모든 애플리케이션 스레드가 멈추기 때문에, 실무에서 응답 지연의 원인이 됩니다. Java 9부터 기본 GC인 G1GC는 Heap을 동적 Region으로 나눠 STW 시간을 줄이고, 초저지연이 필요한 경우 ZGC(STW 1ms 미만)를 사용합니다.

### 꼬리질문
- GC의 동작 과정을 설명해주세요. (Minor GC / Major GC)
- STW(Stop-The-World)란 무엇이고 왜 문제가 되나요?
- Young Generation과 Old Generation의 차이는 무엇인가요?
- G1GC는 기존 GC와 어떻게 다른가요?
- GC 튜닝은 어떻게 하나요?
- ZGC는 어떤 경우에 사용하나요?
