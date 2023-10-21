## 🚢 [Dacon] Titanic Survived 예측 with TeamProject 🚢
- Hapr_final_titanic.ipynb로 확인!    
- https://dacon.io/competitions/open/235539/data
- 최종 정확도 : 0.7628   

#### 🚢 기존 변수 
-PassengerID : 탑승객 고유 아이디   
-Survival : 탑승객 생존 유무 (0: 사망, 1: 생존)   
-Pclass : 등실의 등급   
-Name : 이름   
-Sex : 성별   
-Age : 나이   
-Sibsp : 함께 탐승한 형제자매, 아내, 남편의 수   
-Parch : 함께 탐승한 부모, 자식의 수   
-Ticket :티켓 번호   
-Fare : 티켓의 요금   
-Cabin : 객실번호   
-Embarked : 배에 탑승한 항구 이름 ( C = Cherbourn, Q = Queenstown, S = Southampton)   

### 🚢 결측치 처리 (Null값 처리 in train, test data)
- Age : Pclass 별 평균 나이로 대체   
- Embarked : 결측치 포함한 행 삭제
- Fare : train data에 존재하는 Null값으로 해당되는 Pclass 평균 요금으로 대체
- Cabin : 해당 Pclass, Fare 값 별로 나누어서 cabin 값 대입

### 🚢 최종 모델에 사용한 변수 (Feature Engineering으로 얻은 Features)
- Pclass
- FamilySize : Sibsp + Parch로 만든 새로운 변수
- title : Name에서 호칭(Mr, Miss) 추출하여 만든 새로운 변수
- FareGroup / AgeGroup : Fare/Age 로 만든 새로운 변수 ( Fare가 높을수록 , Age가 낮을수록 생존율 높은 점을 활용)   
- ticket_PC : ticket 앞에 있는 문자열 중 PC의 여부에 따른 새로운 변수 (PC= Private Class)

### 🚢 모델링
- LogisticRegression, DecisionTree, RandomFores, XGBoost, LightGBM 중 LightGBM이 가장 높은 정확도
