# 2022-FSI-data-challenge 금융 데이터 경진대회 


※ 본 프로젝트는 2022 FSI Data Challenge 금융 데이터 경진대회에 참여하여 진행한 데이터 분석 프로젝트입니다. [금융 보안원 주최 공모전으로](https://www.datachallenge2022.com/index.php) 분석 데이터는 주최측에서 제공한 비씨카드-BGF리테일 데이터와, 크롤링한 포켓 CU 리뷰 데이터를 활용하여 분석을 진행하였습니다. 

※ 최종 공모에는 아쉽게 선발되지 못했으나, 본선 진출의 기회를 얻어 PT 발표까지 잘 마무리할 수 있었던 프로젝트였습니다. 


<br>

## 주제 

🚩 엔데믹 진입에 따른 편의점 O2O 실현방안 도출 - 포켓 CU 서비스 My pocket 기획 : 라이프 스타일 기반 상품 추천 

※ (자유주제) 대회 분석용 데이터를 활용한 창의적인 비즈니스 아이디어 또는 문제해결 방법을 제안

<br>

## 기본 정보

<table width=80%>
  <tr><td ><b>팀 이름</b></td><td><b>프로젝트 기간</b></td><td><b>프로젝트원</b></td>
  </tr>
  <tr><td>Cuz</td><td>2022.06.22 ~ 2022.09.26</td><td><A href="https://github.com/hopebii"> 이다현</A>, <A href="https://github.com/kangdy12"> 강다연</A>, <A href="https://github.com/nowionlyseedaylight"> 김나현</A></td>
  </tr>
</table>
<br/>



## 🔹 프로젝트 요약 
자세한 문제점 도출 과정은 <a href="BGF-CU 데이터 발표자료_ Cuz 팀.pdf"> 해당 파일</a>을 참고해주세요
<br/>

![image](https://user-images.githubusercontent.com/77307201/192686158-f1525e55-d037-4879-95d4-2775e547e35a.png)




<table>
  <tr>
    <td width=20%><b>문제 정의</b></td>
    <td>  1. <b>Online to Offline (O2O)</b> 를 통해 고객과의 라스트마일을 줄이고 생활 밀착형 플랫폼으로 성장해가며 <b>Online for Offline (O4O)</b>로의 혁신을 그리는 CU 편의점 <br/><br/>
          2. 빠른 시간에 원하는 물품을 구매할 수 있다는 특징으로 편의점과 경쟁구도를 그리는 퀵커머스 시장</td>
  <tr>
    <td width=20%><b>해결 방안</b></td>
    <td> O2O 서비스 플랫폼을 구축하여 모바일 앱 기능을 고도화 + <b>"라이프 스타일"</b> 기반의 개인화된 상품 추천 = My pocket 기능 고안  </td>
  </tr>
    <tr>
    <td width=20%><b>포켓 CU 리뷰 데이터 분석</b></td>
    <td> 현행 앱인 포켓 CU 에 추가할 기능을 기획한다는 점에서, 기존 포켓 CU 앱에 대한 사용자들의 만족 요인과 불만족 요인을 도출하고자  앱 리뷰 데이터를 분석을 진행하였습니다. <br/><br/>
          <b>🚩 분석 기법 및 절차</b><br/><br/>
          ① PORORO 자연어처리 패키지를 통한 리뷰 평점 재산출 및 감정 라벨링<br/><br/>
          ② 긍부정 키워드 워드클라우드 시각화<br/><br/>
          ③ 이용자의 니즈 및 평가를 심층적으로 분석하기 위한 LDA Topic Modeling</td>
  </tr>
    <tr>
    <td width=20%><b>BC카드 - BGF 사용자 데이터 분석</b></td>
    <td> 제공된 데이터가 약 1300만개의 행에 달하는 큰 크기의 데이터로, 메모리 부족 문제와 서버다운 문제를 해결하기 위해 <b>전처리 - EDA 기반의 1차 필터링 - 모델링 변수중요도 기반의 2차 필터링 -모델링</b> 순서에 맞추어, 분석을 진행하였습니다. 자세한 분석 단계는 발표자료를 참고해주시기 바랍니다. <br/><br/>
          <b>🚩 분석 기법 및 절차</b><br/><br/>
          ① PreProcessing & Feature engineering : EDA 를 통해 전처리를 진행한 후, 주어진 데이터셋을 바탕으로 '단가' 와 '접근성' 칼럼을 추가<br/><br/>
          ② First Filtering : 연구자료 서치 및 EDA 분석 결과를 바탕으로 1차 데이터 필터링을 진행<br/><br/>
          ③ Second Filtering : Random Forest Regressor 로 '결재 고객수' 예측 모델링을 진행하여 변수 중요도를 시각화 해, 예측에 가장 많은 영향을 미치는 상위 변수를 기준으로 2차 필터링을 진행<br/><br/>
          ④ Clustering : 라이프 스타일 기반의 상품 추천을 위해 클러스터링을 진행 : 범주형 변수와 연속형 변수가 혼합된 데이터셋 → K-prototype Clustering 기법 적용<br/><br/>
          ⑤ Recommendataion : Item-based collaborative Filtering 기법으로 상품 간 코사인 유사도 테이블 생성 → 라이프 스타일 특징을 반영한 군집 기반 연관 상품 추천 진행 </td>
  </tr>
  </table>
<br/>



## 1️⃣ 포켓 CU 앱 분석 
- 현행 기능의 장단점을 분석 + 리뷰 텍스트를 분석 → 분석을 통해 얻은 인사이트를 바탕으로 기능 구성에 대한 방향성을 설립함
<br/>


<table>
  <tr>
    <td width=25%><b>현행 기능의 장점 분석</b> : 재고조회, 편PICK 등 구매 불확실성을 낮추는 다양한 기능으로 생활 밀착형 플랫폼으로 발전함</td>
    <td>
    <img src = "https://user-images.githubusercontent.com/77307201/192686762-ea9c412a-f593-4b94-8785-0d4af4ea6bb9.png">
    </td>
  </tr>
  <tr>
    <td width=25%><b>현행 기능의 단점 분석</b> : 여전히 상품 선택의 소요 시간이 존재하며, 존재하는 추천 기능이 개인화되어있지 않음</td>
    <td>
      <img src = "https://user-images.githubusercontent.com/77307201/192686976-e2c99098-3f91-47e0-8e26-d8cb0362668c.png">
    </td>
  </tr>
    <tr>
    <td width=25%><b>리뷰 텍스트 분석</b> : 워드클라우드 시각화, LDA Topic Modeling → 앱에 관한 사용자의 긍부정 요인을 도출</td>
    <td>
      <img src = "https://user-images.githubusercontent.com/77307201/192687210-8d8b500e-9ee2-4d02-98b7-a9522fc298a4.png"></br></br>
      <img src = "https://user-images.githubusercontent.com/77307201/192687287-6e798343-5cd5-4b50-9615-79016107aa77.png">
    </td>
  </tr>
</table>   

</br>

💡 <b>인사이트 활용방안 제시</b></br>

- <b>만족 부분을 최대화</b> : 활성화 되어 주로 사용되는 기능인 재고확인, 단골점포 포인트 적립 및 할인 행사 정보를 추천 상품과 함께 제공 
- <b>불만족 부분을 최소화</b> : 추천 과정에 있어 시간 지연이나 어플의 기능적 결함에 관한 오류 문제를 최소화하기 위해 추천 시스템 실행 시간을 단축하도록 코드를 구성 

</br>

## 2️⃣ 군집 기반 추천시스템 구현 
- Filtering : EDA, 회귀 예측 변수중요도 결과 기준 변수로 필터링 
- Clustering : K-prototype Clustering 으로 필터링 된 테이블을 다시 군집화 하여, 라이프 스타일 기반의 군집별 특징을 도출 
- Recommendation : 클러스터링 기반의 연관 상품 추천 
<br/>


<table>
  <tr>
    <td width=25%><b>테이블 필터링 결과</b></td>
    <td>
    <img src = "https://user-images.githubusercontent.com/77307201/192687978-e181abb8-a66d-48fa-b7f8-04cd0cfd6a78.png">
    </td>
  </tr>
  <tr>
    <td width=25%><b>클러스터링 EDA 결과</b></td>
    <td>
      <img src = "https://user-images.githubusercontent.com/77307201/192688046-fd47efe0-4e4b-4ba0-83ea-94ee21d14c79.png">
    </td>
  </tr>
    <tr>
    <td width=25%><b>추천시스템 Flow</b></td>
    <td>
      <img src = "https://user-images.githubusercontent.com/77307201/192688107-6a7fe5c2-ecfb-4030-af60-d52947496edf.png">
    </td>
  </tr>
</table>   

</br>


## 3️⃣ 앱 기능 시뮬레이션 

- 서울특별시 가족주택 위치 인근 편의점의 초중고 자녀를 둔 40대 고객이 와인/양주 품목을 구매할 때 연관 상품 추천 과정

</br> 

<table>
  <tr>
    <td>
    <img src = "https://user-images.githubusercontent.com/77307201/192688251-f9c00ff0-6f88-4d4f-95be-34fdd29ad26e.png"></br>
    위치기반 서비스 동의와 회원가입 시 입력하는 정보로, 데이터 필터링을 자동화 할 수 있음 
     </td>
  </tr>
  <tr>
    <td>
    <img src = "https://user-images.githubusercontent.com/77307201/192688296-e8d74570-2cb5-4320-869e-7f997f5717dc.png"></br>
    사용자가 와인을 선택한다면 와인과 유사도가 높은 반찬류, 안주류, 디저트류와 같은 범주의 상품들이 뜨게 되면서 / 추가 구매를 유도할 수 있게 됨 
    </td> 
  </tr>
</table>   

→ 군집별 고객의 특성을 반영하여, 보다 개인화 • 라이프스타일에 초점이 맞춰진 추천이 가능해짐 

</br> 

## 4️⃣ 기대효과 

</br>

<table>
  <tr>
    <td width=25%><b>PB 상품 개발 가이드 제시</b></td>
    <td>
    <img src = "https://user-images.githubusercontent.com/77307201/192688468-94e8cb29-21d4-49a8-869b-2dd2e2efadb3.png"></br>
  bgf리테일의 자체 상품 개발에 방향성을 제시 → 노령층의 경우 10시~1시 시간대에 간편식사류 결제수량이 많으므로 노령층의 특성을 고려한 재료를 사용하여 웰빙 연화식 메뉴 개발을 제안할 수 있음 
    </td>
  </tr>
  <tr>
    <td width=25%><b>편의점 로컬라이징 전략 가이드</b></td>
    <td>
      <img src = "https://user-images.githubusercontent.com/77307201/192688644-492f4693-4414-453b-9d4f-844b031235cc.png"></br>
      가령, 최근 2030 세대의 큰 호응을 얻고 있는 비건 상품을 CU 채식주의 간편식 시리즈를 중심으로 비건 특화 매장을 만드는 방안을 제안할 수 있고, 특히 최근 포켓 CU 2차 리뉴얼과 관련한 <b>가맹점 별 특화 매장을 형성</b>하는 데 있어, my pocket 의 라이프 스타일 기반의 추천 기능이 도움이 될 것으로 기대함 
    </td>
  </tr>
    <tr>
    <td width=25%><b>포켓CU 편의성 및 이용자수 증가</b></td>
    <td>
      <img src = "https://user-images.githubusercontent.com/77307201/192690092-1abdb38d-c509-4e97-affb-2ee583548aea.png"></br>
       포켓CU는 리뉴얼을 지속해왔고 그 결과 이전보다 좋은 실적을 내고 있음 → 사용자들이 새로운 기능을 거부감 없이 잘 흡수한다는 것을 의미 →  my pocket 기능도 개인 맞춤형 서비스로 거래의 깊이와 폭을 확장해 신규고객 유치, 앱 사용 시간 증대 등의 효과를 낼 수 있을 것으로 기대함 
    </td>
  </tr>
    <tr>
    <td width=25%><b>잠재상품 판매 및 프로모션 다양화</b></td>
    <td>
      <img src = "https://user-images.githubusercontent.com/77307201/192690230-811d1e04-97e7-4c81-81b4-176e094500c4.png"></br> 
      ‘My Pocket’ 기능을 바탕으로 이전에는 발견하지 못했던 상품들 간의 관계성을 파악하고 이를 통해 특정 상품이 판매될 때 그 상품과 연관성이 높은 상품을 추천함으로써 매출 증대 효과를 기대할 수 있으며 상품 추천에서 더 나아가 프로모션 기획에도 인사이트를 제공할 수 있을 것이라 기대함 
    </td>
  </tr>
</table>  
