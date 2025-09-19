※ 모든 문제는 사용자에게 제공된 CSV 파일의 데이터가 테이블에 모두 들어있다고 가정하고 작성하시오.

users 테이블에서 id, username, phone 컬럼을 모두 조회하시오. (5점)

 

orders 테이블에서 2015년에 주문된 모든 주문의 수를 세시오. (5점)

 

products 테이블에서 price가 가장 비싼 제품의 name을 조회하시오. (5점)

 

users 테이블에서 country가 'Korea'인 회원들의 id와 username을 조회하시오. (5점)

 

staff 테이블에서 birth_date가 1960년 1월 1일 이전인 직원의 last_name과 first_name을 조회하시오. (5점)

 

orders 테이블에서 user_id가 20인 회원이 주문한 모든 주문의 id와 order_date를 조회하시오. (5점)

 

orderdetails 테이블에서 product_id가 17번인 제품의 총 quantity를 계산하시오. (5점)

 

products 테이블에서 price의 평균값을 소수점 둘째 자리까지 반올림하여 조회하시오. (5점)

 

users 테이블에서 country별 회원 수를 계산하고, 회원 수가 5명 이상인 국가만 출력하시오. (5점)

 

orders 테이블에서 staff_id별 주문 건수를 계산하고, 주문 건수가 가장 많은 직원부터 순서대로 staff_id와 주문 건수를 출력하시오. (5점)

 

users와 orders 테이블을 결합하여, 각 회원(users.id)별 주문 건수를 계산하고, 주문 건수가 2건 이상인 회원의 username과 주문 건수를 출력하시오. (10점)

 

12. users와 staff 테이블을 결합하여, 직원인 회원의 id, username, last_name, first_name을 조회하시오. (5점)

 

13. orders와 orderdetails 테이블을 결합하여, 각 주문(orders.id)별 총 주문 수량의 합계를 계산하고, 총 수량이 100 초과인 주문의 order_id와 총 수량을 출력하시오. (10점)

 

14. orders와 users 테이블을 결합하여, country가 'USA'인 회원들이 주문한 총 건수를 계산하시오. (10점)

 

15. orders 테이블에서 주문 날짜가 2015년 12월이면서 staff_id가 3번인 직원이 담당한 주문 건수를 조회하시오. (5점)

 

16. products 테이블에서 price가 products 테이블의 평균 price보다 높은 제품의 name과 price를 조회하시오. (10점)

 

17. users 테이블에서 city별 회원 수를 계산하고, city가 'Seoul'인 회원의 수를 조회하시오. (5점)

 

18. orders, orderdetails, products 테이블을 결합하여, 각 주문(orders.id)별 총 주문 금액(제품 가격(price) * 수량(quantity))을 계산하고, 주문 금액이 2000 이상인 주문의 order_id와 총 금액을 출력하시오. (15점)

 

19. products 테이블에서 name에 'Coffee'가 포함된 제품의 name과 price를 조회하시오. (5점)

 

20. staff 테이블에서 birth_date가 1960년 이전인 직원과 1990년 이후인 직원의 last_name과 first_name을 UNION으로 합쳐서 조회하시오. (10점)

 