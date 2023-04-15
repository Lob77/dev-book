# dev-book
<h2>1. 테이블 생성</h2>

CREATE TABLE develop_book ( <br>
book_id INTEGER, <br>
date DATE, <br>
name VARCHAR(80) <br>
); 
<br><br>

<h2>2. 데이터 베이스 생성 명령어</h2>
CREATE DATABASE 데이터베이스명;
<br><br>

<h2>3. 데이터 베이스 접속 명령어</h2>
\c book_store;

<br>
<h2>4. 데이터 베이스 삭제 명령어</h2>
DROP DATABASE 데이터베이스명;

<br>
<h2>5. 생성한 테이블 리스트 조회 명령어</h2>
\dt

<br>
<h2>6. 테이블에 데이터 추가하기</h2>
INSERT INTO table VALUES(value1, 'value2', 'value3');<br><br>
<h3>**대화형 문구를 넣을 때는 ""로 감싸줄 것!</h3>
INSERT INTO table VALUES(value1, 'value2', '"value3"');<br><br>

<h3>**작은 따옴표를 표현하고 싶을 때는 '''value1'''와 같이 작은 따옴표를 2번 입력해 감싸준다!</h3><br>

<h3>**컬럼 순서별로 데이터를 넣고 싶을 때</h3>
INSERT INTO table (col1, col2, col3) VALUES (value1, 'value2','value3');

<br>
<h2>7. 모든 데이터 조회하기</h2>
 SELECT * FROM table;

<br>
<h2>8. 특정 컬럼 데이터 조회하기</h2>
 SELECT col1, col2 FROM table;
<br>
<h3>**데이터 선택 조회 명령어</h3>
1. LIMIT: 반환하는 로우의 개수를 지정한다.<br>
2. OFFSET: 반환하는 로우의 시작시점을 지정한다.<br>
3. ORDER BY: 반환하는 로우를 정렬할 때 사용한다.<br>
4. WHERE: 지정한 로우만 조회가 되도록 필터기능을 한다.<br>
*** WHERE 절에서 사용되는 비교연산자(=, <>, >, <, >= , <=)

<br>
<h2>9. 서브쿼리</h2>
쿼리문 안에 쿼리가 반복되는 구조<br>
SELECT * FROM table<br>
WHERE 'value1' = (<br>
    SELECT col1 FROM table<br>
    WHERE   value2 = 조건값<br>
);<br>


<br>
<h2>10. 데이터 수정하기</h2>
UPDATE 테이블명<br>
    SET 컬럼명 = 바꿀 데이터 내용<br>
    WHERE 수정할 로우의 조건<br>
RETURNING *;

<br>
<h2>11. 데이터 삭제하기</h2>
DELETE FROM 테이블명 NWHERE 컬럼명 = 삭제할 데이터;

<br>
<h2><실습>기본적인 게시판 관련 데이터베이스 구축</h2>
데이터 베이스명: community_board<br>
CREATE DATABASE community_board;
1. 테이블 명: users<br>
컬럼:user_pk(INTEGER), user_id(VARCHAR(80)), user_pw(VARCHAR(12)), register_dat(DATE)<br>
CREATE TABLE users <br>
(<br>
    user_pk INTEGER PRIMARY KEY,<br>
    user_id VARCHAR(80),<br>
    user_pw VARCHAR(12),<br>
    register_dat DATE<br>
);<br>
2. 테이블 명:boards<br>
컬럼:board_pk(INTEGER), board_user(INTEGER), register_date(DATE), title(VARCHAR(30)) 
CREATE TABLE boards <br>
(<br>
    board_pk INTEGER PRIMARY KEY,<br>
    board_user INTEGER,<br>
    register_date DATE,<br>
    title VARCHAR(30)<br>
);<br>
3. users 테이블에 데이터 삽입하기<br>
INSERT INTO users (user_pk,user_id,user_pw,register_dat) VALUES<br>
    (1,'Carveinus', 'car1234', '2020/04/23'),<br>
    (2,'Jenna', 'kk3375', '2020/07/12'),<br>
    (3,'Wlfur', 'fur0022', '2020/08/31');<br>

/**내용추가할 것
4. boards 테이블에 데이터 삽입하기


