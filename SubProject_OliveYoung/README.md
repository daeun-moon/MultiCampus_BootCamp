![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
### SubProject 주제 : 🌱올리브영 랭킹상품을 토대로 한 시각화🌱
**<분석결과>**    
 🌱 올리브영에서 랭킹을 많이 차지하는 인기있는 브랜드들을 파악 할 수 있다.    
 🌱 가설 설정 : 상품의 가격이 저렴하면, 브랜드의 가격대가 저렴하면 랭킹을 많이 차지하거나 높은 순위를 차지할 것이다.    
     가설과 다르게 상품의 가격과 브랜드의 가격대는 랭킹과는 상관관계가 없다.   
 🌱 실시간으로 특정 제품의 순위 추이를 볼 수 있고, 앞으로의 추이를 예측 해볼 수 있다.  

________
 **1. 판매랭킹 부분 - 브랜드별 랭킹 횟수**
+ 링크 : https://www.oliveyoung.co.kr/store/main/getBestList.do?dispCatNo=900000100100001&fltDispCatNo=&pageIdx=0&rowsPerPage=0
- (1) 크롤링 : BeautifulSoup, HTML에서 CSS 셀렉터 활용하여 정보 추출
- (2) 전처리 : 정가리스트 처리(정가=현재가인 경우 HTML에서 정가태그 존재X)
- (3) 시각화     
      (i) 브랜드별 랭킹에 오른 횟수 내림차순으로 정렬   
   <img src="https://user-images.githubusercontent.com/84755366/222643175-58c92bd9-623a-4d22-804b-966e5941a63d.PNG"   width="800" height="370">         
      (ii) 랭킹에 오른 횟수에 대한 Boxplot    
   <img src="https://user-images.githubusercontent.com/84755366/222644904-16081685-2328-43d0-8970-724b224171c7.PNG"   width="400" height="370">       
      (iii) 상위 25% 브랜드별 랭킹에 오른 횟수   
   <img src="https://user-images.githubusercontent.com/84755366/222647415-36ffaccb-4806-4f39-8c09-09539c2604c6.PNG"   width="400" height="370">           
      (iv) 상위 25%만 Pie Chart로 확인    
   <img src="https://user-images.githubusercontent.com/84755366/222648102-577d2f0a-b1fb-421c-8018-63efa0fc36f0.PNG"   width="400" height="370">   
          
 ________  
 **2. 판매랭킹 부분 - 상관관계 파악**
  + 링크 : https://www.oliveyoung.co.kr/store/main/getBestList.do?dispCatNo=900000100100001&fltDispCatNo=&pageIdx=0&rowsPerPage=0
- (1) 크롤링 : BeautifulSoup, HTML에서 CSS 셀렉터 활용하여 정보 추출
- (2) 전처리 : 상관관계 계산 불가능한 경우(모두 True, False) 조건 처리 ( 미처리시 상관계수 NaN )
- (3) 시각화  
      (i) 옵션(세일, 증정, 쿠폰, 오늘딈)과 순위와의 상관관계 & 브랜드 랭크횟수와의 상관계수    
   <img src="https://user-images.githubusercontent.com/84755366/222650002-d9d6ee42-c791-4e68-ac3e-2ed774c7cfa0.PNG"   width="600" height="370">
   <img src="https://user-images.githubusercontent.com/84755366/222649332-0671ddc0-057b-4cf4-ac14-e3f88b15b06d.PNG"   width="600" height="370">         
      (ii) 가격들(정가,현재판매가)과 순위와의 상관관계, 브랜드 랭크횟수와의 상관관계
   <img src="https://user-images.githubusercontent.com/84755366/222652783-6ef11cb7-afa2-448e-9c76-adf4ed5d5e98.PNG"   width="600" height="370">
   <img src="https://user-images.githubusercontent.com/84755366/222653001-fae9f520-65dd-4b11-94bf-5bf7d7c4befd.PNG"   width="600" height="370">
   ________        
**3. 실시간 랭킹 부분- 특정제품의 순위추이 확인**
 + 링크 : https://www.oliveyoung.co.kr/store/main/getBestList.do?dispCatNo=900000100100004&fltDispCatNo=&pageIdx=0&rowsPerPage=0
- (1) 크롤링 : JSON, Post방식 + HTML에서 CSS 셀렉터 활용하여 정보 추출
- (2) 전처리 : Viewer 수 HTML로 갖고오기
- (3) 시각화 : 특정제품의 꺾은선 그래프를 통해 순위 변화 확인     
  ![g1](https://user-images.githubusercontent.com/84755366/222651685-cc01b608-9b8d-48d1-8e42-3575b95c529a.PNG)
___________
**한계 & 아쉬운 점**   
🌱 크롤링 하는 시점에 따라 데이터가 달라져 분석결과가 좌지우지된다. (옵션들과의 상관계수에서 pvalue값이 넓은 폭으로 달라진다. -> 상관관계 파악 어려움)       
🌱 대량의 데이터를 확보한 후 저장해놨다면 여러 분석에서 정확한 결과를 얻을 수 있었을 것으로 생각된다.      
