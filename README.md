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
 

 ## 2023-04-06

 # 데이터프레임

  - 개념 : 매트릭스와 마찬가지로 2차원 형태의 데이터를 저장하고 분석하는데 사용되는 자료 구조
  - 특징 : 
  (1) 서로 다른 종류의 값이 함께 저장 될 수 있음
  (2) 숫자형 자료와 문자형 자료가 결합되어 있는 형태
  (3) 특정 열을 잘라서 보았을 때 값을의 자료형이 동일해야 함

** city <- c("Seoul", "Tokyo", "Washington") - 문자로 이루어진 벡터
** rank <- c(1,3,2) - 숫자로 이루어진 벡터
** city.info <- data.frame(city, rank) - 데이터프레임 생성

1. iris 데이터 셋
 - 4개의 숫자형 열과 1개의 문자형 열이 결합되어 있음

# 매트릭스와 데이터프레임 다루어보기
1. 데이터셋의 기본 정보 알아보기
 dim(iris) - 행과 열의 개수 보이기
 nrow(iris) -  행의 개수 보이기
 ncol(iris) - 열의 개수 보이기
 colnames(iris) - 열 이름 보이기, name() 함수와 결과 동일
 head(iris) - 데이터셋의 앞부분 일부 보기
 tail(iris) - 데디터셋의 뒷부분 일부 보기

 # 매트릭스와 데이터 프레임에 함수 적용
 - 합계와 평균을 계산할 때 iris[,-5]와 같이 5열을 제외하는 이유
-> 5열은 품종을 나타내는 범주형 자료이다
그래서 팩터 형태로 저장이 되어있는데, 범주형 자료는 합계나 평균 등의 산술연산이 적용될 수 없기 때문이다

# 조건에 맞는 행과 열의 값 추출하기
 - subset() 함수
: 전체 데이터에서 조건에 맞는 행들만 추출하는 기능 제공
 - subset()함수에서 매개변수의 의미 (1) iris : 데이터를 추출하는 대상이 iris 데이터셋입니다 (2) Species == 'setosa' : 데이터를 추출할 조건을 지정하는 부분으로, 품종 열의 값이 'setosa'인 행만 추출하라는 의미입니다

 # 매트릭스와 데이터프레임의 자료구조 확인과 변환

 ## 데이터 입출력
 1. R에서의 입력과 출력
  - 분석 대상이 되는 데이터를 입력한 후 입력된 데이터를 분석하여 필요한 정보를 얻는다. 이렇게 얻은 결과는 사용자가 알기 쉽게 출력된다.
  - R 프로그램에서 데이터의 입력과 결과의 출력은 기본적인 구성 요소

2. Print() 함수와 cat() 함수
 - print() - 하나의 값을 출력할 때, 데이터프레임과 같은 2차원 자료구조를 출력할 때, 출력후 자동 줄바꿈 
 - cat() - 여러 개의 값을 연결해서 출력할 때 벡터는 출력되나 2차원 자료구조는 출력되지 않음, 출력 후 줄바꿈을 하려면 '\n' 필요
 
 ## 2023-04-13
# 조건문

## 1. if-else문
 - 조건문의 기본구조
 if(비교 조건) {
  조건이 참일때 실행할 명령문
 } else {
  조건이 거짓일 떄 실행한 명령문
 }

 ##  ifelse문
  - if-else문을 서술할 때 조건에 따라 선택할 값이 각각 하나씩이면 ifelse문을 이용하는 것이 편리함
  - ifelse문의 문법

# 반복문

## 1. for문
 - for문 기본구조
 for(반복 변수 in 반복 범위) {
반복할 명령문
}
## 1. while문
 - while문 문법
 while (비교 조건){
반복할 명령문(들)
}

## 3. apply() 계열 함수
 - 반복 작업의 대상이 매트릭스나 데이터프레임의 행이나 열인 경우 이용
 - 매트릭스나 데이터프레임에 있는 행들이나 열들이 하나하나 차례로 꺼내어 평균이나 합계 등을 구하는 작업을 수행하고자 할 때 유용
 - apply() 함수 문법
 - apply() 함수에서 사용되는 매개변수의 의미

# 사용자 정의 함수

## 1. 사용자 정의 함수 개념
 - 두 개의 값을 입력받아 둘 중에서 큰 수를 결과값으로 돌려주는 함수

## 2. 사용자 정의 함수의 저장과 재실행
 - 사용자 정의 함수 사용 절차 (1) 함수 작성 (2) 함수를 실행하여 R에 함수 등록 (3) 필요한 곳에서 함수 호출
