# 602377122한만중

## 2023-03-09
1. git 세팅 방법
- git 설치 -> URL : https://git-scm.com/
- github 가입하기
- 원하는 경로에 폴더 생성 -> visual studio code에서 레포지터리 초기화 클릭
- 파일 생성 후 변경사항 스테이징 처리 -> commit -> push 진행
- VSCode 에서 깃허브 연동 -> 로그인 
- github에서 레포지터리 생성되었는지 확인 후 -> push 된 파일 확인

2. 프로그래밍이란?


## 2023-03-16
출장으로 인한 수업 참여 못함


## 2023-03-23
### R 패키지
- R에서의 패키지 -> 라이브러리와 같은 개념
## 변수
- 프로그램 내에서 어떤 값을 저장해 놓을 수 있는 역할

1. R객체의 타입
 - R 객체에는 아래와 같은 종류들이 있다.
   1.atomic(상수)
   2.vector(벡터)
   3.matrix(행렬)
   4.list(리스트)
   5.data.frame(데이터프레임)
   6.function(함수)
   7.operator(연산자)
 - R 객체 중 데이터 객체 : atomic, vector, matrix, data.frame  ⇒ 데이터 객체 (data object)
2. 상수 데이터 객체
 - 상수 데이터 객체의 유형
   1.정수형 
   2.실수형(double)
   3.문자형(character)
   4.논리형(logical)
   5.복소수형(complex number)
   
3. 벡터 (VECTOR)
 - 벡터는 하나 이상의 원소로 이루어진 자료
 - 벡터를 구성하는 각 원소는 그 유형(data type)이 동일해야 함  ⇒ (1,2,"a","b")는 잘못된 벡터
 - 함수를 이용한 벡터의 생성
  * rep : 같은 수 반복
    rep(2, 10) =  [1] 2 2 2 2 2 2 2 2 2 2
    rep(c(1,2), each=5) = [1] 1 1 1 1 1 2 2 2 2 2
  * seq : 등차 수열 생성
    seq(0, 1, length=11) # 0과 1사이를 동일 간격으로 11개의 숫자벡터를 생성
    seq(1, 9, by = 2) # 1에서 9까지 2씩 증가하는 숫자로 이루어진 벡터를 만듬
    numeric, double, integer, character: 속성이 numeric, double, integer, 혹은 character인 벡터를 괄호안의 수만큼 할당함

integer(length = 10) =  [1] 0 0 0 0 0 0 0 0 0 0
 - 벡터의 클래스
    numeric: 연속형
    factor: 범주형
    ordered: 순서있는 범주형

## 2023-03-30

# R Studio 명령어
 - list 조회하기
  is()
 - list 삭제
  rm(해당되는 리스트 명 작성)
 - 전체 list 삭제
  rm(list = ls())

# R에서의 자료구조
 - 1차원 자료 : 백터, 리스트, 팩터 
 - 2차원 자료 : 매트릭스, 데이터프레임

## 1차원 자료 vs 2차원 자료
 - 1차원 자료 : 단일 주제에 대한 값들을 모아 놓은 것
 - 2차원 자료 : 복수 주제에 대한 값들을 모아 놓은 자료

## 범주형 자료 vs 수치형 자료
 - 범주형 자료 : '분류'의 의미를 갖는 값들로 구성된 자료로, 보통 문자로 표현되고 산술연산 적용 X
 -