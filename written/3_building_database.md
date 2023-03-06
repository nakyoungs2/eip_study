# 1장 논리 데이터베이스 설계

### 334p - 4번 : 물리적 데이터베이스 설계에 대한 설명으로 거리가 먼 것은?
1. 물리적 설계의 목적은 효율적인 방법으로 데이터를 저장하는 것이다.
2. 트랜잭션 처리량과 응답시간, 디스크 용량 등을 고려해야 한다.
3. 저장 레코드의 형식, 순서, 접근 경로와 같은 정보를 사용하여 설계한다.
4. 트랜잭션의 인터페이스를 설계하며, 데이터 타입 및 데이터 타입들 간의 관계로 표현한다.
> 정답 : 4번, 트랜잭션의 인터페이스를 설계하고 데이터 타입 및 타입들 간의 관계 표현은 논리적 설계에서 수행한다.

**-> 개념적 설계, 논리적 설계, 물리적 설계의 구분이 중요하다!**

개념적 설계 : 현실 세계에 대한 인식을 추상적인 개념으로 표현하는 과정  
ex) 개념 스키마/트랜잭션 모델링, 요구 조건 명세를 E-R 다이어그램으로 작성, 독립적 개념 스키마 설계

논리적 설계 : 현실 세계의 자료를 컴퓨터가 이해/처리하기 위해서는 물리적 저장장치에 저장되어야 한다.  
이를 위해 특정 DBMS가 지원하는 논리적 자료 구조로 변환시키는 과정  
ex) 개념 세계의 데이터를 데이터 타입과 데이터 타입들 간의 관계로 표현, 개념 스키마를 평가/정제하고 서로 다른 논리적 스키마 설계  
트랜잭션의 인터페이스, 테이블 설계

물리적 설계 : 논리적 자료 구조를 물리적 구조의 데이터로 변환  
ex) 데이터베이스 파일의 저장 구조/액세스 경로 결정, 레코드와 같은 정보를 사용하여 데이터가 컴퓨터에 저장되는 방법 묘사
***
### 371p - 5번 : 관계대수에 대한 설명으로 틀린 것은?
1. 주어진 릴레이션 조작을 위한 연산의 집합이다.
2. 일반 집합 연산과 순수 관계 연산으로 구분된다.
3. 질의에 대한 해를 구하기 위해 수행해야 할 연산의 순서를 명시한다.
4. 원하는 정보와 그 정보를 어떻게 유도하는가를 기술하는 비절차적 방법이다.
> 정답 : 4번, 관계대수는 관계형 데이터베이스에서 원하는 정보와 그 정보를 검색하기 위해 어떻게 유도하는지를 기술하는 절차적인 언어이다. 원하는 정보가 무엇이라는 것만 정의하는 비절차적 언어는 관계해석이다.

**-> 관계대수 VS 관계해석 구분하기!**

관계대수 : 관계형 데이터베이스에서 원하는 정보와 그 정보를 검색하기 위해 어떻게 유도하는가를 기술하는 절차적 언어

관계해석 : 관계 데이터의 연산을 표현하는 방법으로 원하는 정보가 무엇이라는 것만 정의하는 비절차적 특성을 가짐
***
# 2장 물리 데이터베이스 설계

### 414p - 4번 : 데이터베이스에서의 뷰(View)에 대한 설명으로 틀린 것은?
1. 뷰는 다른 뷰를 기반으로 새로운 뷰를 만들 수 있다.
2. 뷰는 일종의 가상 테이블이며, UPDATE에는 제약이 따른다.
3. 뷰는 기본 테이블을 만드는 것처럼 CREATE VIEW를 사용하여 만들 수 있다.
4. 뷰는 논리적으로 존재하는 기본 테이블과 다르게 물리적으로만 존재하며 카탈로그에 저장된다.  
> 정답 : 4번, 뷰는 물리적으로 존재하는 기본 테이블과 다르게 논리적으로만 존재하며, 기본 테이블과 마찬가지로 카탈로그에 저장된다.

**-> 뷰의 의미, 특징, 장/단점 모두 중요하다!**

<뷰의 의미>  
- 사용자에게 접근이 허용된 자료만 제한적으로 보여주기 위해 하나 이상의 기본 테이블로부터 유도된, 이름을 가지는 가상 테이블
- 물리적으로 존재하지는 않지만 사용자에게 있는 것처럼 간주된다.  
- 임시적인 작업을 위한 용도로 활용된다.
- 조인문 사용의 최소화로 사용상의 편의성을 최대화한다.
- **뷰를 생성하면 뷰의 정의가 시스템 내에 저장되었다가 생성된 뷰 이름을 질의어에서 사용할 경우 질의어가 실행될 때 뷰에 정의된 기본 테이블로 대체되어 기본 테이블에 대해 실행된다.**

<뷰의 특징>
- 기본 테이블로부터 유도된 테이블이므로 기본 테이블과 같은 형태의 구조를 사용하며, 조작도 기본 테이블과 거의 같다.
- 가상 테이블로 물리적으로 구현되어 있지 않다.
- 데이터의 논리적 독립성을 제공할 수 있다.
- 필요한 데이터만 뷰로 정의/처리할 수 있으므로 관리가 용이하고 명령문이 간단해진다.
- **뷰를 통해서만 데이터에 접근하게 하면 뷰에 나타나지 않는 데이터를 안전하게 보호하는 효율적인 기법으로 사용할 수 있다.**
- 기본 테이블의 기본키를 포함한 속성 집합으로 뷰를 구성해야만 삽입, 삭제, 갱신 연산이 가능하다.
- **일단 정의된 뷰는 다른 뷰의 정의에 기초가 될 수 있다.**
- 뷰가 정의된 기본 테이블이나 뷰를 삭제하면 그 테이블이나 뷰를 기초로 정의된 다른 뷰도 자동으로 삭제된다.
- 뷰를 정의할 때는 CREATE문, 제거할 때는 DROP문을 사용한다.

<뷰의 장점>
- 논리적 데이터 독립성을 제공한다.
- 동일 데이터에 대해 동시에 여러 사용자의 상이한 응용/요구를 지원해준다.
- 사용자의 데이터 관리를 간단하게 해준다.
- 접근 제어를 통한 자동 보안이 제공된다.

<뷰의 단점>
- 독립적인 인덱스를 가질 수 없다.
- **뷰의 정의를 변경할 수 없다.**
- **뷰로 구성된 내용에 대한 삽입, 삭제, 갱신 연산에 제약이 따른다.**