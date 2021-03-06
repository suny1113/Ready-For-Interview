# Database
* [데이터베이스란?](#db-1)
* [SQL이란?](#db-2)
* [DML, DDL, DCL, 트랜잭션이란?](#db-3)
* [관계형 데이터베이스](#db-4)
* [데이터베이스 정규화](#db-5)
* [기본키와 외래키](#db-6)
* [Join 이란?](#db-7)
* [서브쿼리란?](#db-8)
* [WHERE과 HAVING의 차이](#db-9)
* [View란?](#db-10)
* [GROUP BY](#db-11)
* [ORDER BY](#db-12)
* [Primary Key와 Unique Key 차이점](#db-13)
* [Inner Join과 Outer Join의 차이점](#db-14)
* [기본키, 외래키, 인덱스의 의미와 어떻게 사용할지?](#db-15)
* [Oracle vs MySQL?](#db-16)



## 데이터베이스란? <a id="db-1" />
컴퓨터 시스템에 전자적으로 저장되는 구조화된 정보, 데이터의 모음이다.<br>
DBMS를 통해 데이터베이스를 관리하며 응용 프로그램들이 데이터베이스를 공유하며 사용할 수 있는 환경을 제공해준다.<br>
장점은 데이터의 중복을 최소화 할 수 있고, 표준화되어있어 체계적인 사용이 가능하고, 일관성, 무결성, 보안성 등의 장점이 있다.<br>
단점은 다양한 유형의 데이터가 서로 연관되어있어 복잡하고 시스템 자원을 많이 사용해 운영비가 증가하는 등의 단점이 있다.

## SQL이란? <a id="db-2" />
Structured Query Lanaguage의 줄임말로, 관계형 데이터베이스 시스템에서 자료를 관리 , 처리하기 위해 설계된 언어이다.<br>

## DML, DDL, DCL, 트랜잭션 <a id="db-3"/>
- DML (Data Manipulation Language) : 데이터를 추가, 수정, 삭제하기 위한 데이터 관리 언어 (커밋 필요)
- DDL (Data Definition Language) : 테이블과 같은 데이터 구조를 정의하는데 사용하는 데이터 정의 언어 (auto commit)
- DCL (Data Control Language) : 데이터베이스에 접근하고 객체를 사용할 권한을 주고 회수하는 데이터 제어 언어 (auto commit)
- 트랜잭션이란 데이터베이스의 상태를 변화시키기 위해 수행하는 작업의 단위이며 하나의 작업을 처리하기 위해 여러가지의 연산 작업이 필요할 수 있다.
- 이러한 트랜잭션을 통제하는 언어는 TCL이라 하며 Commit, Rollback이 있다.

## 관계형 데이터베이스<a id="db-4"/>
열과 행으로 이루어진 테이블에 서로 관련된 데이터를 모아 관리하는 데이터베이스의 한 유형이다.

## 정규화<a id="db-5"/>
하나의 테이블에 중복된 데이터가 저장될 때, 중복이 늘어날수록 검색에 시간이 오래걸리고 용량이 커질 수 있다.<br>
테이블을 분할해서 데이터의 불필요한 중복을 제거하기 위해 정규화가 필요하다.<br>
- 1정규화 : 하나의 컬럼은 하나의 값만 가질 수 있다.
- 2정규화 : 부분적 함수 종속 제거
- 3정규화 : 이행적 함수 종속 제거

## 기본키와 외래키<a id="db-6"/>
### Primary Key
1. 테이블에 저장된 행을 식별할 수 있는 유일한 값이여야 한다.
2. 중복될수 없고, null이 올 수 없다.

### Foreign Key
1. 특정 테이블에 포함되어 있으면서 다른 테이블의 PK로 지정된 값을 의미한다.
2. 다른 테이블을 참조할 때 사용하는 키이다.(반드시 외부 값들 중 하나를 참조해야함)

## Join <a id="db-7"/>
서로 관련있는 두 개 이상의 테이블을 연결시켜주는 방법이며 최소 테이블갯수-1개의 조건을 만족해야 한다.
  
## 서브쿼리 <a id="db-8"/>
하나의 SQL문에 포함되어 있는 또 다른 SQL문
- SELECT 절 : 스칼라 서브쿼리, 서브쿼리 결과는 단일값
- FROM 절 : 인라인 뷰, 결과는 하나의 테이블로 리턴
- WHERE 절 : 단일행 서브쿼리(단일행 비교연산자), 다중행 서브쿼리(다중행 비교연산자)
  
## WHERE절과 HAVING절의 차이 <a id="db-9"/>
- WHERE, HAVING 둘 다 조건절이지만<br>
  WHERE절은 FROM절 뒤에 위치하고 모든 필드에 조건을 줄 수 있는 반면에 HAVING절은 GROUP BY 절에서 그룹화 되어진 테이블에 조건을 줄 수 있다.

## View란? <a id="db-10"/>
실제 테이블이 아닌 가상 테이블이며 원본 테이블에 가서 데이터를 불러오는 Query문이라 할 수 있다.<br>
저장장소를 거의 사용하지 않는 가상 테이블이며 논리적으로 테이블과 같은 역할을 한다.<br>
### View의 장점
- 원본 테이블의 일부만 view로 만들어 사용자에게 편의성 제공
- 보여져서는 안되는 중요한 데이터를 view에서 제외시켜 보안성 강화
- 조인을 쓰는 경우가 많을 때 view를 생성해두고 필요할때마다 조회하면 편리
  
## GROUP BY <a id="db-11"/>
복수행 함수를 출력할 때 GROUP BY 절에서 특정한 컬럼을 조건으로 사용해 세부적인 그룹화를 할 수 있다.<br>
각 그룹에 대해 합계, 평균, 개수 등의 함수를 적용 가능하다.
  
## ORDER BY <a id="db-12"/>
SELECT문의 가장 마지막에 위치하고 있으며 실행 순서와 작성 순서가 모두 마지막이다.<br>
조회된 데이터들을 다양한 목적에 맞게 특정 컬럼을 기준으로 정렬하는데 사용한다. 기본적으로 오름차순 정렬.
  
## PK vs UK <a id="db-13"/>
둘 다 테이블 내에서 유일성을 보장하는 키이지만 차이점은, <br>
- Primary Key는 테이블 내에서 한개만 생성이 가능하고, 중복된 값, null값이 올 수 없다.
- Unique Key는 테이블 내에 여러개 생성이 가능하고, 중복된값이 올 수 없지만 null값은 허용된다.
  
## Inner Join vs Outer Join <a id="db-14"/>
Inner Join은 테이블 간의 공통된 데이터들만 검색된다.(교집합)<br>
Outer Join은 테이블 간의 전체 데이터를 검색하는데 누락된 데이터도 같이 표기된다.<br>
Outer Join은 Full Outer Join, Left Outer Join, Right Outer Join 세 종류가 있다.
- Full Outer Join은 왼쪽, 오른쪽 테이블의 모든 데이터들이 검색된다.
- Left Outer Join은 왼쪽 테이블을 기준으로 Join하는 것이고, 왼쪽테이블의 모든 데이터와 오른쪽 테이블에서 중복된 데이터들이 검색된다.
- Right Outer Join은 오른쪽 테이블을 기준으로 Join하는 것이고, 오른쪽테이블의 모든 데이터와 왼쪽 테이블에서 중복된 데이터들이 검색된다.
  
## 기본키, 외래키, 인덱스에 대한 내 생각 <a id="db-15"/>
모든 테이블에서 데이터 작업(수정이나 삭제)을 하기 위해 저장된 데이터들을 식별할 수 있는 PK 는 필수로 지정해야 한다. <br>
외래키는 두 개의 테이블을 연결하는 역할을 하며 무결성을 높이기 위해 서로 관련있는 테이블이라면 지정하는게 맞다.<br>
인덱스는 데이터의 양이 많아질 때 검색 속도를 빠르게 하기 위해 생성하고 기업에서 사용하는 DB는 대용량 데이터가 많을 것이기 때문에 Index의 사용을 알아둬야 한다고 생각한다.<br>
인덱스의 원리는 해당 컬럼에 index를 걸어준 다음 ROWID를 보고 테이블에 접근하는 방식, ROWID를 이용해 데이터를 가장 빠르게 검색할 수 있다.<br>
주로 자주 검색되는 컬럼이나, 조인조건으로 자주 사용되는 컬럼에 index를 걸어준다.

## Oracle과 MySQL <a id="db-16"/>
Oracle은 큰 규모의 예산과 복잡한 비즈니스 요구와 기업을 위해 설계되었고, <br>
MySQL은 데이터베이스 기반 웹 사이트에 사용되는 저가형 데이터베이스이다.<br>
기업은 자사에 적절한 비용등과 같은 기준을 산정해 데이터베이스를 선정할 것이다.<br>
ANSI SQL문은 표준 SQL문이기 때문에 DBMS의 종류에 영향을 받지 않고, 다른 DBMS를 배우더라도 금방 배울 수 있다.
