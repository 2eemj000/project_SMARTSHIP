# ML/DL-SpringBoot-React-project
머신러닝 / 딥러닝 + 스프링 부트 + 리액트 - 웹페이지

## 💡 프로젝트 소개
### 선박, 육상, 공급업체간 기부속/선용품 공급망 관리 시스템
```
해운선사, 선박(구매자), 공급업체(판매자) 간의 역할에 맞춰 시스템을 구축하여
기부속 및 선용품의 판매, 주문, 공급 과정을 원활하게 관리하고자 함.
```
### (+) 선용품 카테고리 분류 및 리드타임 예측 서비스
```
선용품 등록 시, 추천 카테고리 분류를 통한 등록
‘리드타임’ : 육상에서 물건을 주문(발주)하고 해당 물건이 창고로 입고되기까지의 시간
선용품을 너무 일찍 발주할 경우 -> 불필요한 보관비용이 발생
선용품을 너무 늦게 발주할 경우 -> 선박 운영에 차질이 발생할 수 있음
다양한 선용품의 리드타임을 예측하여 최적의 발주 시점을 찾아 보관 및 운영에 드는 비용을 최소화하고자 함.
```

## 🕰️ 개발 기간
* 24.08.23. - 24.10.08.

## ⚙️ 개발 환경
- `Java 17.0.10`
- `JDK 17.0.10 `
- **React** : 18.2.0
- **IDE** : STS4
- **Framework** : Springboot 2
- **Database** : MySQL 8.0.37
- **Machine Learning / Deep Learning** : BERT, BertTransformer, XGBClassifier, Lightbgmregressor

## 📌 주요 기능
#### [공통] 회원가입 / 로그인 / 회원탈퇴
- 회원가입 시 회원유형 선택 (해운선사,  공급업체, 선박)
- 아이디 중복확인 및 비밀번호 유효성검사 포함
- 로그인 시 ID 저장 기능
  
#### [선박] 선용품 리스트  &  장바구니 & 주문 내역
- 구매가능한 모든 물품 열람가능
- 카테고리별 필터링 기능, 물품명 검색 기능
- 장바구니 담기 기능 (주문건당 메모 첨부 가능)  
- 창고 출고 예정일 선택 후 주문 신청 가능
- 구매 요청 내역 및 발주 상태 확인 기능 (발주 예정, 진행, 완료 표기)
  
#### [해운선사] 대시보드
- 공지사항을 통한 해당 사이트 이용에 대한 변경 및 수정사항 확인
- 최근 4개의 구매 요청건의 선박명 및 희망입고일 확인
- 최근 5개의 주문건에 대한 창고 출고 일정 및 발주상태 확인
- 최근 5개의 주문건에 포함된 물품의 과거 리드타임 시각화

#### [해운선사] 발주 요청 내역 & 발주
- 발주 요청 내역을 주문일자 기준 최신순으로 정렬하여 확인 가능
- 각 요청 내역 클릭 시, 요청 물품 목록 상세 내역 확인 및 발주하기 가능
- 사용자가 입력한 창고 출고 예정일까지 수령 불가능한 상품을 표기 및 대체가능한 상품 추천
- 각 물품에 대한 과거 리드타임, 요청건 전체 물품 목록에 대한 예상 리드타임 시각화 (리드타임 예측모델 활용)

#### [해운선사] 일정 관리
- 발주 내역을 달력으로 시각화
- 각 일정 클릭 시, 발주한 물품 상세 내역 확인 가능

#### [공급업체] 대시보드
- 공지사항을 통한 해당 사이트 이용에 대한 변경 및 수정사항 확인
- 최근 3일 이내의 주문 요청 확인 
- 판매물품에 대한 category1, category2, category3 분포 시각화
- 판매량 Top10 물품 확인 및 판매량 시각화

#### [공급업체] 판매물품 리스트
- 판매 중인 모든 물품 열람가능
- 카테고리별 필터링 기능, 물품명 검색 기능
- 각 항목별 상세정보 수정 가능, 삭제 가능, 판매여부 변경 가능
- 신규 상품 등록 기능 (카테고리 분류 모델 활용)


|Home|(선박)구매요청|(해운선사)대시보드|(해운선사)요청건별 품목 및 리드타임 확인-Model1|
|---|---|---|---|
|![로그인](https://github.com/user-attachments/assets/7e08dd1d-02d2-42ba-92b7-5e58028ef9ba)|![구매요청내역](https://github.com/user-attachments/assets/4409c019-2d13-4aba-8f91-ab03d3913868)|![해운선사대시보드+리드타임](https://github.com/user-attachments/assets/5de51580-b91c-459c-a8f8-c6bc43b828a1)|![발주목록확인+리드타임확인](https://github.com/user-attachments/assets/49229cf7-4cb4-446d-83f9-131d2eee12ec)|
|선박/해운선사/공급업체 Role 별 회원가입 및 로그인 |선박은 창고출고일 지정 후 선사에 구매요청| 발주요청 품목 리스트 / 출고일정 / 리드타임 확인 가능|요청 건별 목록 조회|

|(해운선사)대체상품 확인 |(해운선사)품목의 과거 리드타임 확인 |(공급업체)대시보드|(공급업체)기자재 등록-Model2|
|---|---|---|---| 
|![대체상품확인](https://github.com/user-attachments/assets/99bf4390-e584-4502-8d21-8c8dd4601ad9)|![품목별 과거리드타임확인](https://github.com/user-attachments/assets/62a2a0b7-f608-4c2e-8c55-73b0a2b086be)|![공급업체자기물건확인](https://github.com/user-attachments/assets/eeaffd17-445b-4a57-8798-cd2ac655d3fb)|![기자재 등록](https://github.com/user-attachments/assets/138ce76c-397f-4d4c-9c85-9738280ed41c)|
|리드타임 over로 인하여 지정창고입고일에 입고가 불가능한 경우 alert=> 대체상품 추천|품목별 과거 리드타임 차트|공급업체로 들어온 주문 관리 및 조회|새로운 기자재 등록 시 카테고리 추천 분류|


[![Watch the video](https://github.com/user-attachments/assets/37ef937e-c45e-415d-8793-32359c2f86ed)](https://www.youtube.com/watch?v=drF5rMgZzB0)

SMARTSHIP 웹 페이지 시연 영상입니다.

## Project Summary

### Aug 30, 2024
- 프로젝트 리포지토리 관리 시작
- 화면 구성을 위한 figma 화면 구현
- DB 구성, 기능 정의

### Sep 1, 2024
- ListTable 수정 (목업데이터를 코드안에서 관리함)
- `/ListTable` 페이징기능 수정 (카테고리 조건 및 검색 조건 시 알맞게 페이지로 조정되도록)
- 네비게이션과 푸터, 화면배경 조정
  
### Sep 2, 2024
- Calendar 검색 기능 추가
- Event 일정 추가

### Sep 3, 2024
- Order 수정 및 DB 연결 시도
- ListTable, Order 기능 수정
- Schedule Modal 수정
- GradientButton 컴포넌트 생성

### Sep 4, 2024
- Schedule 수정
- OrderTest 파일 생성
- ListTable 검색 버튼 추가 및 기능 수정
- fetch코드 구현 (백엔드 연결 준비)
  
### Sep 5, 2024
- SignIn, SignUp 기능 수정
- Schedule 서버 연결 완료
  
### Sep 6, 2024
- ListTable 수정
- 로그인 백엔드 연결

### Sep 7, 2024
- ListTable UI 수정 및 Footer 수정
- MUI Card 스타일 수정

### Sep 8, 2024
- ListTable (선택품목 모아보기, 체크박스 동작 수정)

### Sep 9, 2024
- Order 수정
- ListTable 기능 수정 (수량을 입력받아 가격띄움) 및 토글 버튼 생성
- 02폴더 내에 json파일을 따로 생성해서 fetch 기능 확인하며 수정하도록 변경
  
### Sep 10, 2024
- ListTable 수정
- SignState 생성
- Datepicker 수정

### Sep 11, 2024
- Nav 수정
- ListTable DB 연결 완료
- `/ListTableDB`에서 같은 카테고리, 같은 itemname은 하나만 띄우기 위해 각 행에 대한 아이디를 정함
- `/ListTableDB`에서 itemId, itemName을 구분해서 함수 정의
- 02폴더와 03폴더내의 scss중복 해결 (적용시킬 각 js파일내의 최상위컴포넌트에 className을 설정하여 scss파일의 최상위에 이름을 추가함)

### Sep 12, 2024
- Order 삭제 기능 완료
- ListSupplier 페이지 생성

### Sep 13, 2024
- Order, OrderTest 수정
- Order Datepicker 및 Checkbox 수정 완료
- category, part, itemName이 모두 같은 상품의 supplier가 유일하면(1개라면) 바로 해당하는 공급업체, 가격이 떠있도록 useEffect 추가
- 리드타임 차트 출력에 대한 페이지 추가 고려

### Sep 15, 2024
- Recommend HTML 및 Fetch 기능 완성
- Order Checkbox, 버튼 기능 완성

### Sep 16, 2024
- Recommend 수정

### Sep 19, 2024
- ListTable 수정
- `/ListTableDB`에서 공급업체로 로그인했을때에는 해당하는 공급업체에서 등록한 물품만 뜨지만 등록, 수정이 가능하기 위해서는 category, part 등은 db의 모든 항목을 받아와야하므로 restapi를 분리함
- Order 수정
- 화면 구성 변경 (기존에 선박에서 상품을 결정하여 공급업체(판매자), 가격이 확정되어 해운선사에 전달되는 시스템에서 -> 선박에서 상품명과 수량, 요청사항을 전달하면 해운선사에서 리드타임, 요청사항을 바탕으로 상품을 결정하는 시스템으로 변경)

### Sep 20, 2024
- `/OrderTest`에서 백엔드 연결완료
- `/ListTableDB`에서 검색버튼 클릭 전 검색어입력만으로 테이블 안의 항목이 필터링됨 -> 핸들러함수를 버튼으로 옮겨서 버튼기능 수정
- PurchaseRequestList 완성
- MyOrderList 완성

### Sep 22, 2024
- `/ListTableDB`에서 페이징기능 수정 (항목이 없는 페이지도 아래 페이지버튼이 생성됨 -> 카테고리 선택 및 검색 후 필터링된 최종 행의 수를 페이지당 항목 수로 나누어 올림한 값으로 변경)
- `/OrderTest`에서 페이징기능 구현
- Modal2.js를 컴포넌트로 따로 분리하여 코드 간소화

### Sep 23, 2024
- `/ListSupplier2`에서 해당 공급업체의 아이템만 가져올 때(물품 검색, 테이블 출력)에는 "/finditem/${itemId}"를, 전체 카테고리 목록 가져올 때(테이블의 각 행에서 카테고리 변경 시)에는 "/category1","/category2","/category3" RestAPI를 사용하도록 구분
- listtabledb에서 담은 물품이 없을때 담기가 불가하도록 수정
- 판매자가 여러개인 상품에서 선택안했을 시 장바구니 담기 예외처리

### Sep 24, 2024
- "/finditem"에서 판매여부도 넘겨받아 스위치 토글 버튼으로 가시화, 변경가능하도록 수정
- `/ListSupplier2`에서 필터링, 검색기능, 전체선택 기능 고치기
- textfield에서 검색 버튼 눌러야 해당하는 목록으로 필터링되도록 수정
- 삭제("supplier/{itemsId}", 저장 ("supplier/items/{itemsId}")할 때, 여러 아이템을 한번에 삭제, 수정되도록 배열로 넘겨받도록 수정

### Sep 25, 2024
- `/ListTableDB`에서 수량 전달 수정
- `/OrderTEST`에서 필터링, 검색, 페이징기능 수정

### Sep 26, 2024
- 장바구니에서 넘겨줄때 하나를 다시 두개로 풀어서 보내기

### Sep 27, 2024
- member별 아이디 추가, 아이디 중복확인 기능 추가
- flask와 연결할 카테고리 추천 페이지 생성
- flask 연결 완료
- `/finditem` 페이지에서 "saveToOrder/${orderdate}" 넘겨줄 때, 주문한 요일도 같이 넘기도록 추가

### Sep 30, 2024
- 카테고리 추천 모달 수정
- Navi에 회원탈퇴 버튼 및 기능 추가

### Oct 1, 2024
- `/ListSupplier2`의 새상품 등록 카테고리 추천 모달 완성

### Oct 2, 2024
- 생성한 페이지 로딩창, 경고창 추가하기
- 신규상품등록에 입력값 비어있을때 경고창 띄우고 해당모달 그대로 띄워두도록 수정
- `/ListSupplier2` 페이지 No.값 수정
- `/ListSupplier2` 페이지에서 새로고침하면 뜨는 showAlert 에러 해결 (App.js에서 AlertProvider는 모든 라우트가 정의된 Routes 안에 있어야함 -> 자식 컴포넌트에서 useAlert를 안전하게 사용할 수 있게됨)

### Oct 3, 2024
- 판매자 대시보드 `/SupplierBoard`에 차트 "itemSupplier" 추가 (물품목록의 카테고리를 category1,2,3에 따른 원그래프로 가시화)
- 판매자 대시보드 `/SupplierBoard`에 차트 "itemTop10" 추가 (판매량이 가장 높은 10개의 상품에 대한 판매량을 막대그래프로 가시화)

### Oct 4, 2024
- `/SupplierBoard`의 차트에서 fetch 받을 때 token 추가하여 각 공급업체에 해당하는 아이템만 띄우도록 수정
- 차트 css 수정

### Oct 6, 2024
- 판매자 대시보드 `/SupplierBoard`에 공지사항 추가
- 판매자 대시보드 `/SupplierBoard`에 각 공급업체의 최근 3일치 주문요청내역 "itemOrderList" 추가
- 생성한 페이지 로딩창, 경고창 추가하기
