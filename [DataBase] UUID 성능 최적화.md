# 1. 비교 Auto increment vs UUID as Primary Key

## 1-1. Auto increment

- 장점 : 단순 증가값(Sequential)이기 때문에 데이터에 접근할 때의 리소스가 적게 든다.
- 단점 : PK(ID)값을 노출하는 경우의 보안 이슈

## 1-2. UUID

- 장점 : 보안
- 단점 : 성능(느리다). 긺.

---

# 2. Solution

UUID를 사용하면서 최적화할 수 있는 방법에 대해 알아봤다. 

1. Indexing
2. Data Size

## 2-1. Indexing

UUID v4의 경우 랜덤값이기 때문에 DB 입장에서는 삽입 되는 값의 순서가 없이 무작위로 값이 들어오기 때문에 이를 정렬하는 데에 부담이 크다. 

(기본적으로 Primary Key는 **Clustered Index**로 사용되기 때문에 indexing의 대상이다.)

특히 테이블의 데이터 양이 많고 새로 쌓이는 데이터도 많을 때 indexing으로 인해 DB의 성능이 저하될 수 있다.
![image](https://user-images.githubusercontent.com/57996351/177388284-8a6bf31d-8839-4da1-920a-b0079ea0e325.png)

- **Sequential UUID**로 Indexing하는 비용을 줄인다.
    
    쉽고 빠르게 적용해볼 수 있는 방법 중 하나로 **UUID를 랜덤하게 생성하되 이 값을 Sequential 하게 생성**하는 방법이 있다. 
    
    값이 연속적으로 들어오기 때문에 DB 입장에서 새로운 데이터가 들어오더라도 indexing할 때의 비용이 랜덤값일 경우보다 줄어든다. 
    
- Sequencial UUID 생성하기
    1. MySQL function
        - Sequential UUID 생성하는 function 만들어서 사용
    2. Java 
        - Java Uuid Generator (JUG) Library 이용
    3. Node.js
        - uuid-sequential Library 이용

## 2-2. Data Size

![image](https://user-images.githubusercontent.com/57996351/177388218-426b2807-b4de-412b-bb9a-69bb48d7ced3.png)


MySQL 기준, **BIGINT 8-bytes**, UUID는 **CHAR**로 처리할 경우 **36-bytes**

⇒ UUID 쓰면 그만큼 데이터 더 필요하다.

- **UUID_TO_BIN 또는 UNHEX**를 사용해 **BINARY**로 처리할 경우엔 **16-bytes**로도 처리할 수 있다.
- BIGINT < **BINARY** < CHAR 로 처리하는 경우의 데이터 크기
    - 물론 BIGINT로 처리할 때보다 데이터가 크지만 CHAR로 처리할 때보다 절반 이상의 데이터를 줄일 수 있다.
- 다만, SELECT 시 BINARY 값이므로 사람이 읽을 수 있도록 값을 변환하는 과정 필요할지도..

참고

[https://www.percona.com/blog/2014/12/19/store-uuid-optimized-way/](https://www.percona.com/blog/2014/12/19/store-uuid-optimized-way/)
