# INNER JOIN과 OUTER JOIN

## Q. INNER JOIN과 OUTER JOIN의 차이는 무엇인가요?

### 답변
INNER JOIN은 두 테이블에서 조인 조건이 일치하는 행만 반환하고, OUTER JOIN은 조건이 일치하지 않는 행도 NULL로 채워 함께 반환합니다.

예를 들어 회원 테이블과 주문 테이블을 조인할 때, INNER JOIN은 주문이 있는 회원만 결과에 나오고 주문이 한 번도 없는 회원은 제외됩니다.
반면 OUTER JOIN은 주문이 없는 회원도 결과에 포함시키고, 주문 관련 컬럼은 NULL로 채웁니다.

그래서 두 테이블에 모두 존재하는 데이터만 필요할 때는 INNER JOIN을, 한쪽 테이블 기준으로 빠짐없이 데이터를 봐야 할 때는 OUTER JOIN을 사용합니다.

### 꼬리질문

**Q. LEFT JOIN과 RIGHT JOIN은 어떻게 다른가요?**

A. 둘 다 OUTER JOIN의 종류로, LEFT JOIN은 왼쪽 테이블의 모든 행을 기준으로 오른쪽 테이블을 매칭시키고, RIGHT JOIN은 반대로 오른쪽 테이블의 모든 행을 기준으로 합니다.
실무에서는 RIGHT JOIN 대신 테이블 순서만 바꿔 LEFT JOIN으로 통일해서 쓰는 경우가 많습니다.

**Q. FULL OUTER JOIN은 무엇인가요?**

A. 두 테이블의 모든 행을 반환하는 조인으로, 어느 한쪽에서라도 매칭되지 않으면 그 자리를 NULL로 채웁니다.
LEFT JOIN 결과와 RIGHT JOIN 결과를 합친 것과 같은 결과를 얻을 수 있습니다.

**Q. JOIN 조건에 WHERE 대신 ON을 쓰는 이유는 무엇인가요?**

A. ON은 조인이 이루어지기 전에 매칭 조건을 걸고, WHERE는 조인이 끝난 결과에 필터를 거는 차이가 있습니다.
INNER JOIN에서는 결과가 같지만, OUTER JOIN에서 WHERE에 조건을 걸면 NULL로 채워진 행까지 걸러져 OUTER JOIN을 쓴 의미가 사라질 수 있습니다.
