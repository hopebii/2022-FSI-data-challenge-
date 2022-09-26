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
  <tr><td>Cuz</td><td>2022.06.22 ~ 2022.09.26</td><td><A href="https://github.com/hopebii"> 이다현</A>, <A href="https://github.com/kangdy12"> 강다연</A>, <A href=" "> 김나현</A></td>
  </tr>
</table>
<br/>



## 프로젝트 요약 
자세한 문제점 도출 과정은 <a href=" "> 해당 파일</a>을 참고해주세요
<br/>

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
          (1) PORORO 자연어처리 패키지를 통한 리뷰 평점 재산출 및 감정 라벨링<br/><br/>
          (2) 긍부정 키워드 워드클라우드 시각화<br/><br/>
          (3) 이용자의 니즈 및 평가를 심층적으로 분석하기 위한 LDA Topic Modeling</td>
  </tr>
    <tr>
    <td width=20%><b>BC카드 - BGF 사용자 데이터 분석</b></td>
    <td> 제공된 데이터가 약 1300만개의 행에 달하는 큰 크기의 데이터로, 메모리 부족 문제와 서버다운 문제를 해결하기 위해 <b>전처리 - EDA 기반의 1차 필터링 - 모델링 변수중요도 기반의 2차 필터링 -모델링</b> 순서에 맞추어, 분석을 진행하였습니다. 자세한 분석 단계는 발표자료를 참고해주시기 바랍니다. <br/><br/>
          <b>🚩 분석 기법 및 절차</b><br/><br/>
          (1) PreProcessing & Feature engineering : EDA 를 통해 전처리를 진행한 후, 주어진 데이터셋을 바탕으로 '단가' 와 '접근성' 칼럼을 추가<br/><br/>
          (2) Fist Filtering : 연구자료 서치 및 EDA 분석 결과를 바탕으로 1차 데이터 필터링을 진행<br/><br/>
          (3) Second Filtering : Random Forest Regressor 로 '결재 고객수' 예측 모델링을 진행하여 변수 중요도를 시각화 해, 예측에 가장 많은 영향을 미치는 상위 변수를 기준으로 2차 필터링을 진행<br/><br/>
          (4) Clustering : 라이프 스타일 기반의 상품 추천을 위해 클러스터링을 진행 : 범주형 변수와 연속형 변수가 혼합된 데이터셋 → K-prototype Clustering 기법 적용<br/><br/>
          (5) Recommendataion : Item-based collaborative Filtering 기법으로 상품 간 코사인 유사도 테이블 생성 → 라이프 스타일 특징을 반영한 군집 기반 연관 상품 추천 진행 </td>
  </tr>
  </table>
<br/>

