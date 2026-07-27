# GC (Garbage Collection)

## Q. GC(Garbage Collection)란 무엇인가요?

### 답변
GC는 JVM Heap 메모리에서 더 이상 참조되지 않는 객체를 자동으로 정리해주는 메커니즘입니다.
개발자의 메모리 관리 부담과 누수 위험을 줄여주지만, 실행 중 모든 스레드가 멈추는 STW(Stop-The-World) 현상이 발생해 애플리케이션 지연의 원인이 되기도 합니다.
이를 줄이기 위해 JVM은 객체 대부분이 생성 직후 사라진다는 특성을 활용해 Heap을 Young과 Old Generation으로 나눠 GC 범위를 최소화합니다.


### 꼬리질문
- GC의 동작 과정을 설명해주세요. (Minor GC / Major GC)
- STW(Stop-The-World)란 무엇이고 왜 문제가 되나요?
- Young Generation과 Old Generation의 차이는 무엇인가요?
- G1GC는 기존 GC와 어떻게 다른가요?

---

## Q. GC의 동작 과정을 설명해주세요. (Minor GC / Major GC)

### 답변
새 객체는 Eden에 생성되고, Eden이 가득 차면 Minor GC가 실행됩니다.
살아남은 객체는 Survivor를 거쳐 Old Generation으로 승격되고, Old Generation이 가득 차면 Major GC가 실행됩니다.
Minor GC는 STW가 짧지만, Major GC는 Heap 전체를 대상으로 해 STW가 길어 응답 지연에 직접 영향을 줍니다.

---

## Q. STW(Stop-The-World)란 무엇이고 왜 문제가 되나요?

### 답변
STW는 GC 실행 중 JVM이 모든 애플리케이션 스레드를 강제로 멈추는 현상입니다.
이 시간 동안 요청 처리가 중단되므로, 사용자 입장에서 응답 지연으로 직결됩니다.

---

## Q. Young Generation과 Old Generation의 차이는 무엇인가요?

### 답변
Young Generation은 새로 생성된 객체를 담으며, Minor GC가 자주 실행되지만 STW가 짧습니다.
Old Generation은 오래 살아남은 객체를 담으며, Major GC는 드물지만 Heap 전체를 대상으로 해 STW가 깁니다.

---

## Q. G1GC는 기존 GC와 어떻게 다른가요?

### 답변
기존 GC는 Heap을 Young/Old 고정 영역으로 나눴지만, G1GC는 Heap을 동일 크기의 Region으로 분할합니다.
GC가 필요한 Region을 우선 수집해 STW 시간을 예측 가능한 수준으로 줄이는 것이 핵심입니다.

