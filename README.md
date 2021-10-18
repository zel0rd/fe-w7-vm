# Web 자판기
Observer Pattern을 이해하고 그를 적용한 Web자판기를 만든 web 서비스입니다.

[JavaScript, express, Webpack]

## 📌프로젝트 구현

![화면 기록 2021-03-26 오전 12 16 10 mov](https://user-images.githubusercontent.com/71919983/112497231-c4395780-8dc8-11eb-90b2-4ffdd26c5848.gif)


## 📌프로젝트 정보

### 문제 해결과 개선 과정

|주제|링크|내용요약|
|------|---|---|
|문제&해결|[🔗고민과제들](https://github.com/ink-0/fe-w7-vm/wiki/%EB%AC%B8%EC%A0%9C%EC%A7%81%EB%A9%B4-&-%ED%95%B4%EA%B2%B0%EA%B3%BC%EC%A0%95)|문제상황들과 그 해결 과정을 위한 시도|
|회고|[🔗프로젝트회고](https://github.com/ink-0/fe-w7-vm/wiki/%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%ED%9A%8C%EA%B3%A0)|프로젝트 회고와 배운점|
|협업|[🔗협업 과정](https://github.com/ink-0/fe-w7-vm/wiki/%ED%98%91%EC%97%85%EB%B0%A9%EC%8B%9D%EA%B3%BC-%EA%B3%BC%EC%A0%95)|커뮤니케이션과 협업의 기록|

### 관련 링크
[🔗 팀 notion](https://www.notion.so/TAMIYOUNG-Vending-Machine-e338788e1b924384ad901def197143f1#e930fe5daf89456ab9c9e8de040387cf) 

[🔗 팀 convention](https://github.com/ink-0/fe-w7-vm/wiki) 


### 팀 구성 

|FE|
|---|
|Young|
|Tami|
  
## 📌파일 구조

<img width="772" alt="스크린샷 2021-06-30 오전 2 21 15" src="https://user-images.githubusercontent.com/71919983/123840918-edc6c980-d949-11eb-9397-53a0db51dd9f.png">

)

<details>
<summary>파일구조 이미지</summary>
<div markdown="1">
  
![스크린샷 2021-06-30 오전 2 23 07](https://user-images.githubusercontent.com/71919983/123841103-1fd82b80-d94a-11eb-885a-e18cff9c2e10.png)

  
</div>
</details>

Model, View, Data로 크게 나누어져 있으며 View는 Model을 구독하며 렌더링의 책임만 하과 Model은 Data의 내용을 관리하고 변경하는 역할을 한다.  

## ✨ 우리팀의 자랑할 점 
#### 사용자 시나리오에 따른 모델 뷰 시나리오 점검
<img width="824" alt="스크린샷 2021-06-30 오전 2 21 22" src="https://user-images.githubusercontent.com/71919983/123840924-eef7f680-d949-11eb-8af7-83b54cebf921.png">
<img width="795" alt="스크린샷 2021-06-30 오전 2 21 28" src="https://user-images.githubusercontent.com/71919983/123840927-f0292380-d949-11eb-88fd-e95e96f5a662.png">




## 📌 기술 요구 사항

### 1️⃣ node, express 설정    
### 2️⃣ html css 구조 짜기   
### 3️⃣ model 객체 ( 지갑, 상품정보 ),  view객체(진행화면)  
### 4️⃣ 동작 구현    

[기본동작](#기본동작)    
[상품 선택할 경우](#상품-선택할-경우)    
[상품 선택 안할 경우](#상품-선택-안할-경우)  
[재고 관리](#재고-관리)    


### 동작 상세설명

#### 기본동작
- [x] `지갑화면`( 동전 누르기) -> `진행화면` (동전 금액 표시) ,`지갑화면`(동전갯수 ,총액변경)    

#### 상품 선택할 경우
- [x] 투입된 금액 충족 -> `상품화면` (<u>구매할 수 있는 상품</u>_(총액<=상품가격)_ 표시)
상품선택 -> 2초 뒤 `진행화면`('바나나 우유'가 선택됨)

#### 상품 선택 안할 경우
- [ ] 돈투입후 5초마다 입력 확인 -> `진행화면` (잔돈 '500원'반환) -> `지갑화면` (잔돈 채워짐)

#### 재고 관리
- [x] 재고 관리(local storage?)
- 자판기 내부에서 관리
- (재고>0)일 때 만 <u>구매할 수 있는 상품</u>에 표시


### ❖ 주의사항
* 모든 이벤트 진행화면(메세지창)표시
* 5초마다 동전 입력 


### 체크리스트
#### Day1
- [x] express, webpack, babel 연동하기
#### Day2
- [x] html, css 작업하기
- [x] 지갑 만들기 (지갑에 돈 설정 + 버튼 누르면 진행화면에 금액 띄우기 + 되돌리기 기능)
#### Day3
- [x] 구매 가능 상품 표시하기 ()
#### Day4
- [x] 구매 여부에 따른 동작 구현 ()

### 기본동작
- [x] **금액 투입** : `Wallet`(개수선택) -> `Screen` (동전 금액 표시) ,`Wallet`(동전갯수 ,총액변경)    
- [x] **상품 구매** : `Product` (구매가능 상품 표시) -> 2초 뒤 `Screen` (상품 선택 표시)
상품선택 -> 2초 뒤 `진행화면`('바나나 우유'가 선택됨)
- [x]  **재고관리** : `Product`(재고 없는 상품 제외 한 구매 가능 상품 표시)

Model|View|
|:---:|:---:|
|WalletModel|WalletView|
|ProductModel|ProductView|
|-|ScreenView|





