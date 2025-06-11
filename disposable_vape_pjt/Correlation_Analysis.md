| 상관분석은 통계학에서 두 변수 간의 선형적인 관계를 분석하는 방법. 두 변수 간의 연관성이 있는지, 그리고 있다면 그 관계가 어떤 방향과 강도로 나타나는지를 파악하는 데 사용됨. 

3. 연관 규칙 마이닝(Association Rule Mining)
3.1 지표 선정
Support(지지도):
Support
=
두 제품 동시 구매 트랜잭션 수
전체 트랜잭션 수
Support= 
전체 트랜잭션 수
두 제품 동시 구매 트랜잭션 수
 

'하카B'의 낮은 매출 비중을 고려해 0.1%~1% 임계값 설정

Lift(향상도):
Lift
=
Confidence
Support(시그니처)
Lift= 
Support(시그니처)
Confidence
 

Lift > 3일 경우 강한 양의 상관관계로 해석

PMI(점별 상호정보량):
PMI
=
log
⁡
2
(
P
(
시그니처
∩
하카B
)
P
(
시그니처
)
P
(
하카B
)
)
PMI=log 
2
 ( 
P(시그니처)P(하카B)
P(시그니처∩하카B)
 )

PMI > 0: 우연적 동시구매보다 유의미한 관계

3.2 알고리즘 선택
Apriori 알고리즘:

python
from mlxtend.frequent_patterns import apriori
frequent_itemsets = apriori(df_onehot, min_support=0.001, use_colnames=True)
최소지지도(min_support)를 0.1%로 설정해 소규모 제품 포함

FP-Growth 알고리즘:

대용량 데이터 처리에 효율적이며, Apriori 대비 10배 빠른 성능