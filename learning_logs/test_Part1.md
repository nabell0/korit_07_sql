sql_finals라는 이름의 데이터베이스를 생성하시오. (1점)

 

앞서 생성한 sql_finals 데이터베이스를 사용하겠다고 지정하시오. (1점)

 

users 테이블을 생성하시오. 컬럼 정보는 다음과 같습니다. (5점)

id : 정수형(INT), 주 키(PRIMARY KEY), 자동 증가(AUTO_INCREMENT)

created_at : 문자열(VARCHAR(100))

username : 문자열(VARCHAR(100)), NULL을 허용하지 않음(NOT NULL)

phone : 문자열(VARCHAR(100))

country : 문자열(VARCHAR(50))

 

users 테이블에 is_marketing_agree라는 이름의 정수형(INT) 컬럼을 추가하시오. (3점)

 

users 테이블의 phone 컬럼명을 user_phone으로 변경하고, 자료형은 그대로 유지하시오. (3점)

 

users 테이블에서 created_at 컬럼을 삭제하시오. (3점)

 

products 테이블을 생성하시오. 컬럼 정보는 다음과 같습니다. (5점)

id : 정수형(INT), 주 키(PRIMARY KEY), 자동 증가(AUTO_INCREMENT)

name : 문자열(VARCHAR(255)), NULL을 허용하지 않음(NOT NULL)

price : 소수점(DECIMAL(10, 2)), NULL을 허용하지 않음(NOT NULL)

discount_price : 소수점(DECIMAL(10, 2)), NULL을 허용하지 않음(NOT NULL)

 

products 테이블의 name 컬럼의 자료형을 VARCHAR(500)으로 변경하시오. (3점)

 

staff 테이블을 생성하시오. 컬럼 정보는 다음과 같습니다. (5점)

id : 정수형(INT), 주 키(PRIMARY KEY), 자동 증가(AUTO_INCREMENT)

user_id : 정수형(INT), NULL을 허용하지 않음(NOT NULL)

last_name : 문자열(VARCHAR(50)), NULL을 허용하지 않음(NOT NULL)

first_name : 문자열(VARCHAR(50)), NULL을 허용하지 않음(NOT NULL)

birth_date : 날짜형(DATE)

 

orders 테이블을 생성하시오. user_id와 staff_id에 외래 키(FOREIGN KEY) 제약 조건을 추가하시오. (5점)

id : 정수형(INT), 주 키(PRIMARY KEY), 자동 증가(AUTO_INCREMENT)

user_id : 정수형(INT)

staff_id : 정수형(INT)

order_date : 날짜형(DATE)

 

orderdetails 테이블을 생성하시오. order_id와 product_id에 외래 키(FOREIGN KEY) 제약 조건을 추가하시오. (5점)

id : 정수형(INT), 주 키(PRIMARY KEY), 자동 증가(AUTO_INCREMENT)

order_id : 정수형(INT)

product_id : 정수형(INT)

quantity : 정수형(INT), NULL을 허용하지 않음(NOT NULL)

 

users 테이블에서 is_marketing_agree 컬럼을 삭제하시오. (3점)

 

orderdetails 테이블의 quantity 컬럼명을 amount로 변경하시오. (3점)

 

orderdetails 테이블을 삭제하시오. (1점)

 

sql_finals 데이터베이스를 삭제하시오. (1점)