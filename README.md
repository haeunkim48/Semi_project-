# Jeju Tourism Project 

### 프로젝트 설명
이 프로젝트는 "제주 여행에 대한 관광객 수 현황 및 인기 관광지 정보 및 현 트렌드 제공"을 주제로 1개월동안 진행한 프로젝트이다. 기간은 2023년 9월 6일부터 2023년 9월 26일까지 진행하였고, 언어는 Python 과 colab 을 사용하였다. 6명의 인원이 한 팀으로, 인기 관광지 파트, 만족도 조사, PPT, 성수기/비성수기, 물가 그리고 Streamlit 파트로 나뉘어 진행하였다. 자세한 설명은 아래를 참조하길 바란다. 


### 선택한 대주제 : 국민 여행조사 데이터를 활용한 여행 유형 분류
#### 주제 변천사 

1. 여행유형을 국내로 한정
   + 2020년부터 2022년까지 기간을 3년으로 잡고 국내여행에 대한 수요가 증가하는 추세라는 가설을 생각함.
   + 코로나 이후 국내여행 증가추세로 관광지별/월별 여행 유형 분류 및 분석, 회귀 분석 후 연관된 독립변수들을 유형으로 삼아 시각화하는 것을 목표로 함.
2. API 사용을 위해 여러 관광지별로 축소하는 것으로 주제 변경.
   + 피드백으로 제주도 같은 한 지역을 기준으로 삼아 코로나 시기를 전/후를 비교한다거나 지역 물가 상승률같은 여행과 연관된 부분들 활용을 추천받음.
3. 피드백 수용 = 제주도로 지역 한정함.
   + API를 사용하는데에도 제주로 지역을 한정하는 것이 도움됨.
   + 코로나 시기 전/후의 제주 여행의 차이(타격, 해외여행과의 비용차이 등)에 대해 통계 분석(회귀 분석까지)을 하는 것을 기준으로 삼음.
   + 제주공항의 혼잡도 정보, 제주 여행 내국인 및 외국인 관광객 현황 등의 핵심 데이터를 API 중심으로 먼저 수집.
4. 3번의 주제를 그대로 이끌고 가되 머신러닝을 사용해보는 것을 추가로 생각함.
   + 비슷한 주제에 대한 논문 수집 및 사용된 분석 기법 참고.
5. 3번의 주제를 그대로 두고, 종속변수를 확정함.
   + 월별 매출을 근거 or 관광객 수 통계를 근거 => 관광객 수를 종속변수로 삼음.
   + 매출액이나 관광객에 얼마나 영향을 미치는 가에 대한 독립변수를 지정한 회귀분석 방향성 제시.
   + 타겟층을 누구로 할 것인지 지정
     + 제주 관광 공사 및 코로나 영향에 대한 논문과 기사를 쓰려는 분들. 
6. 최종 주제로 변경 = 코로나를 제외 시킨 제주 여행에 대한 관광객 수 현황 및 인기 관광지 정보 및 현 트렌드 제공.
   + 코로나를 기준으로 삼는 것이 가장 적절해 보였으나, 실질적으로 데이터를 찾는 것에 한계를 부딪히고 코로나가 가장 심했던 일부 시기의 데이터는 없었음.
   + 수집 가능했던 데이터를 기준으로 관광객 수의 큰 차이를 보지 못해 주제 파기.

- 역할
  + 현재 각 파트당 역할을 분담함.
    + 날씨 파트 >> 인기 관광지 파트로 변경됨(23.09.13) : Sang-Hyeok-Lee(https://github.com/Sang-Hyeok-Lee), SangMingyu(https://github.com/SangMingyu)
    + 만족도 조사(23.09.19) : Sang-Hyeok-Lee(https://github.com/Sang-Hyeok-Lee)
    + PPT : SangMingyu(https://github.com/SangMingyu), HaJeong-K(본인)
    + 성수기/비성수기 파트 : Ezraelyes(https://github.com/Ezraelyes), HWANHEECHO(https://github.com/HWANHEECHO)
    + streamlit : HWANHEECHO(https://github.com/HWANHEECHO)
    + 물가 파트 : HaJeong-K(https://github.com/HaJeong-K), Grace Kim(본인)


## 목표

- 통계 분석 사용.
  + 원 주제로는 코로나 전/후로 나눠서 t-test를 실시하려 했으나, 물가파트에서는 종속변수가 월 평균 지출금액, 독립변수가 4년치에 해당해서 t-test를 시행할 수 없어 AVNOVA 실시.
  + 성수기 파트에서는 만족도 척도를 사용해 요인분석이 어려워 t-test 실시.
- 회귀 분석 사용.
  + 4년간의 각 월별 평균 지출값과 그 지출값에 영향을 미치는 것으로 추정되는 독립변수를 5개를 뽑아 선형 회귀 분석을 진행함.
  + 머신러닝 sklearn의 LinearRegression 사용.
- 예측 구현.
  + 2022년의 데이터가 없어서 이 부분의 값을 추정해 추이를 보는 것으로 사용.
  + 원 주제에서는 사용할 생각이 없었으나, 주제가 거듭 변경이 되면서 최종적으로 예측을 사용함.
  + 머신러닝 sklearn의 train_test_split 사용.
 
### Project Description
This project was carried out for a month under the theme of "Providing the Current Status of the Number of Tourists on Jeju Travel, Information on Popular Tourist Destinations, and Current Trends." The period was from September 6, 2023 to September 26, 2023, and Python and Colab were used as languages. Six people were divided into popular tourist destinations, satisfaction surveys, PPT, peak/low season, prices, and Streamlit parts as a team. Please refer to the following for detailed explanations.


### Topic selected: Classification of travel types using national travel survey data
#### the history of subject change

1. Limited travel type to Korea
+ Considering the hypothesis that the period from 2020 to 2022 is set at three years and the demand for domestic travel is increasing.
+ As a trend of increasing domestic travel after Corona, it aims to classify and analyze travel types by tourist destination/monthly, and to visualize related independent variables as types after regression analysis.
2. Topic change to reduce by multiple tourist destinations for API use.
+ As a feedback, we are recommended to compare the COVID-19 period before and after based on a region such as Jeju Island, or to use travel-related parts such as regional inflation.
3. Accepting feedback = Limited to Jeju Island.
+ It is helpful to limit the area to Jeju even when using API.
+ Based on statistical analysis (up to regression analysis) of differences in Jeju travel before and after the COVID-19 period (bashing, cost difference with overseas travel, etc.).
+ Core data such as congestion information at Jeju Airport and the status of domestic and foreign tourists traveling to Jeju Island are collected first, focusing on API.
4. I think I'm going to take the topic 3 as it is, but I'm going to think about using machine learning additionally.
+ Collect papers on similar topics and note the analytical techniques used.
5. Leave the topic 3 as it is, and determine the dependent variable.
+ Based on monthly sales or statistics on the number of tourists, => The number of tourists is the dependent variable.
+ Presenting the direction of regression analysis designating an independent variable for how much it affects sales or tourists.
+ Specify who to target layer
+ Those who want to write papers and articles on Jeju Tourism Corporation and Corona impact.
6. Change to the final topic = Provide information on the number of tourists and popular tourist destinations for Jeju travel excluding Corona and current trends.
+ It seemed most appropriate to base Covid on it, but there was no data from some of the periods when Covid was most severe, with limits on finding data in practice.
+ Destroying the subject because there is no significant difference in the number of tourists based on the data that could be collected.

- Roles
+ Divided roles for each part at present.
+ Weather Part >> Changed to Popular Tourist Destinations (23.09.13): Sang-Hyeok-Lee (https://github.com/Sang-Hyeok-Lee), SangMingyu (https://github.com/SangMingyu)
  + 만족도 조사(23.09.19) : Sang-Hyeok-Lee(https://github.com/Sang-Hyeok-Lee)
  + PPT : SangMingyu(https://github.com/SangMingyu), HaJeong-K(본인)
  + 성수기/비성수기 파트 : Ezraelyes(https://github.com/Ezraelyes), HWANHEECHO(https://github.com/HWANHEECHO)
  + streamlit : HWANHEECHO(https://github.com/HWANHEECHO)
  + 물가 파트 : HaJeong-K(https://github.com/HaJeong-K), Grace Kim(myself)


## Goals

- Use statistical analysis.
+ The original theme was to conduct t-test before and after Corona, but in the price part, the dependent variable corresponds to the average monthly expenditure and the independent variable corresponds to four years' worth, so AVNOA is conducted.
+ In the peak season part, it is difficult to analyze factors using a satisfaction scale, so t-test is conducted.
- Enable regression analysis.
+ Linear regression analysis is conducted by selecting five independent variables estimated to affect each monthly expenditure value for four years and the expenditure value.
+ Using LinearRegression by Machine Learning Sklearn.
- a predictive implementation.
+ There is no data for 2022, so it is used to estimate the value of this part and see the trend.
+ I didn't intend to use it in the original subject, but as the subject changed over and over again, I finally used prediction.
+ Use train_test_split in machine learning sklearn.

## 개발 로그 기록

[2023.09.11]

- 오늘 한 일
  + 날씨 : 18~22년까지의 월별 방문객 데이터와 강수량 데이터 통합.
  + 성수기 : 2022년 여름시즌 사전, 사후조사 데이터 수집.
  + 물가 : 2018~19년 데이터 수집 완료.

- 오늘 못한 일
  + 날씨 : 강수량에 따른 항공기 결항 상황이나 결항에 따른 입도객 차이수 확인.
  + 성수기 : 2022년 여름시즌 사전, 사후조사 데이터 전처리.
  + 물가 : 2020~21년 데이터 수집 및 일부 데이터 전처리 시작.

- 내일 할 일
  + 날씨 : 결항관련 데이터 수집.
  + 성수기 : 2022년 여름시즌 사전, 사후조사 데이터 수집.
  + 물가 : 2020~21년 데이터 수집 및 모든 데이터 전처리 시작.

- **Trouble-shooting**
  + **날씨 부분만 현재 코드가 진행됨.**
  + 모든 목적별 방문객의 합을 변수로 갖는 전체 방문객 컬럼을 만드는 과정에서 합계 수치가 과도하게 크게 나타나 일부 변수 대상 문자열 -> 숫자열 변환 시행


[2023.09.12]

- 오늘 한 일
  + 날씨 : 항공기 결항 및 실내 관광지 데이터 탐색, 확인, 입도객 데이터와 대조, 강수량별 전체 관광객 비교 .
  + 성수기 : 2022년 사전/사후조사 데이터 전처리.
  + 물가 : 2018년 프로파일, 항공 경비 관련 일부 전처리/2019년 프로파일, 지출경비 관련 일부 전처리.

- 오늘 못한 일
  + 날씨 : 날씨 데이터 자체가 전체 관광객에 영향을 별로 미치지 못한다는 결론이 도출되어 실패된 케이스로 돌아가버림, 그렇기에 다른 변수 및 내용을 탐색해봄.
  + 성수기 : 데이터 차이 관련하여 해결하지 못함, 전처리 일부 미완.
  + 물가 : 2018년, 2019년 데이터 전처리 일부 딜레이.

- 내일 할 일
  + 날씨 : 쓸만한 새로운 데이터(변수)를 찾거나, 다음 주제인 관광지 탐색파트를 미리 탐색해보기.
  + 성수기 : 월간 보고서와 다른 데이터간의 차이 관련 토의, 다른 년도 월별 입도/방문객 데이터 전처리 등.
  + 물가 : 2018, 19년 데이터 남은 전처리 + 2020,21 년 데이터 전처리 시작.

[2023.09.13]

- 오늘 한 일
  + 인기 관광지 : 제주 인기 관광지 탐색 및 데이터 수집(trip.com, trip advisor 등 제주 추천 관광지 직접 추출), 크롤링 or 텍스트마이닝과 워드클라우드 진행해보기.
  + 성수기 : 2022년 사전/사후조사 데이터 전처리 추가작업, 2020-2022 방문 관광객 월간 보고서 파일 다운로드 후 테이블 데이터 일부 전처리.
  + 물가 : 2018, 2019, 21년 전처리 마무리, 2020년, 2022년 전처리 시작.

- 오늘 못한 일
  + 인기 관광지 : 결과가 정상적으로 출력되지 않음  사실상 실패.
  + 성수기 : 월간 보고서에서 활용할 데이터 토의 및 데이터 전처리.
  + 물가 : 2020년 데이터 전처리 마무리.

- 내일 할 일
  + 인기 관광지 : 데이터수집을 더하거나 크롤링, 텍스트마이닝을 다듬어 전체 데이터 워드클라우드 출력까지 확인해보기.
  + 성수기 : 활용 데이터 확정 및 전처리 마무리.
  + 물가 : 2020년, 2022년 전처리 마무리 + 통계분석 시작.

- **Trouble-shooting**
  + 물가 파트 전처리 과정에서 csv파일을 pandas DF로 읽어오는 것에 실패함 => 인코딩의 문제가 있었음.
    + 해결방법을 찾아 해결함.
  + 인기 관광지 목록을 텍스트 마이닝해서 워드 클라우드를 활용하는데 한글이 깨지는 현상이 일어남 > matplotlib.font_manager 참고해서 해결함.

[2023.09.14]

- 오늘 한 일
  + 인기 관광지 : 제주 관광지 데이터 추가수집, 텍스트마이닝 및 워드클라우드 마무리 지도시각화 시작 및 관광지별 상세내용 페이지 추가 작업.
  + 성수기 : 2022년 사후조사 데이터 전처리 일부, 여름월간 보고서 활용 데이터 확정, 테이블 및 이미지 데이터 추출 후 전처리.
  + 물가 : 2020년 전처리 마무리 + 데이터 전처리 합본 + 물가데이터 방향성잡기 (2022년은 예측으로 돌려서 추정으로 활용 + 통계분석 방향은 분산분석으로 확정).

- 오늘 못한 일
  + 인기 관광지 : 관광지 지도시각화 마무리.
  + 성수기 : 2022년 사후조사 데이터 전처리 마무리, ipynb파일 docstring 작성하기.
  + streamlit : streamlit 틀 만들기.
  + 물가 : 데이터 전처리 부분의 추가 설명부분 미완 + 통계분석 시작 못함.

- 내일 할 일
  + 인기 관광지 : 워드클라우드에 사용된 관광지들 지도시각화에 추가작업 및 다음작업 or 관광지 데이터 수집.
  + 성수기 : 2022년 사후조사 데이터 전처리 마무리 후 업로드, ipynb파일 docstring 작성하기.
  + streamlit : streamlit 구체화하기.
  + 물가 : 데이터 전처리 파트 최종 완료 + 시각화와 가설설정.

- **Trouble-shooting**
  + 지도 시각화를 진행하며 관광지 아이콘의 형태가 바뀌지 않는 경우가 존재
  + 아이콘의 색 또한 바뀌지 않는 경우가 존재
    + 공식 Document 및 스택오버플로우를 참고해서 명령어를 변경해서 문제 해결
    + 컬러는 Folium 라이브러리 공식 문서를 참조해도 지정해둔 색을 제외하면 적용이 안됌 > 따로 색을 추가할 필요가 있어보임

[2023.09.15]

- 오늘 한 일
  + 인기 관광지 : 셀레니움을 사용해 5회 이상 언급된 6개 관광지 대상으로 각각 리뷰 110개씩 추출(trip advisor),
        konlpy를 통해 형태소 분리 후 stopwords 작성하여 리뷰 데이터 텍스트 마이닝 중, 크롤링 및 텍스트 마이닝을 진행한 모든 제주 관광지 지도시각화 완료.
  + 성수기 : 월간 보고서 데이터 전처리 ipynb파일 docstring 작성하기.
  + streamlit : streamlit 큰 틀 구성하기.
  + 물가 : 최종 합본 전처리 설명부분 수정 + 시각화 활용방안 모색.

- 오늘 못한 일
  + 성수기 : 사후조사 데이터 전처리 마무리.
  + 물가 : 가설 설정 미완.

- 내일 할 일
  + 인기 관광지 : 텍스트 데이터 추가수집에 대한 결정, 전체 데이터 대상 텍스트 마이닝 작업 필요.
  + 성수기 : 전처리 완료된 데이터 수합하기.
  + streamlit : 전처리 완료된 데이터 수합하여 streamlit에 올려두기, streamlit 페이지 꾸미기.
  + 물가 : 시각화와 가설설정.

- **Trouble-shooting**
  + 물가데이터 시각화 활용 중 데이터 결측치로 인한 plotly 라인이 표시되지 않음.
    + 이 방법을 해결하기 위해서는 수집한 원데이터 자체에 데이터를 채워넣는 방법이 가장 확실했음 > 코드로 채우려했으나, matplotlib은 성공했지만 plotly는 구현하는 것에 문제가 있었음.
  + matplotlib을 사용했을 때도, 결측치와 한글 인코딩 이슈가 나타남 > 한글의 경우 나눔 고딕 폰트를 설정했고, 결측치는 코드를 구현해서 제로값으로 채워 그래프 표현함.
    + 해결방법을 찾아 해결함.

[2023.09.16]

- 오늘 한 일
  + 물가 : 세부 지출 비용에 대한 각 연도별 비교 시각화 \- matplotlib 선그래프.

- 내일 할 일
  + 물가 : 가설 설정 > 시각화를 바탕으로 구체화.

[2023.09.17]

- 오늘 한 일
  + 물가 : 분산분석에 대한 부분 추가.

- 내일 할 일
  + 물가 : 가설 설정 및 채택, 분산 분석 완료 및 회귀분석 시작.

[2023.09.18]

- 오늘 한 일
  + 인기 관광지 : 6가지 관광지를 코드에 적용 및 스탑워드 작성.
  + PPT : PPT 개요파트 사전작업 및 PPT에 사용할 자료조사, 참고자료 조사. 
  + 성수기 : 2022 사후조사 데이터 전처리, 2022 사전조사 일부 시각화, 성수기와 관광객 수의 관계에 대한 가설검정.
  + streamlit : streamlit 페이지 일부 꾸미기.
  + 물가 : 결측치 보간법 채택, 활용법 작성 및 결측치 채우기, 다시한 전처리를 바탕으로 박스플롯 구현, 일원 분산분석 시작(내일 방향성 회의 후 검토 예정), 카테고리별 회귀 산점도 그리기(내일 방향성 회의 후 검토 예정).

- 오늘 못한 일
  + PPT : 사용한 데이터 소개페이지 작성 및 그 외 모든 내용. 
  + 성수기 : 2022 사전/사후조사 시각화 마무리.
  + streamlit : 전처리 완료된 데이터 수합하여 streamlit에 올려두기.
  + 물가 : 가설 검정 마무리.

- 내일 할 일
  + PPT : 현재까지 사용하고, 완성된 데이터를 활용한 PPT 페이지 작성.
  + 성수기 : 2022 사전/사후조사 시각화 완료.
  + streamlit : 전처리 완료된 데이터 수합하여 streamlit에 올려두기.
  + 물가 : 물가파트의 종속변수에 대한 변동부분 회의, 가설 채택 및 부가 설명, 회귀 분석.

- **Trouble-shooting**
  + 물가데이터 박스플롯 시각화를 진행하며 labels와 positions 크기 호환이 안되는 이슈 발생.
    + 해결방법을 찾아 해결함. 
  + 분산분석을 진행하며 자잘한 이슈가 발생함.
    + 해결방법을 찾아 해결함.

[2023.09.19]

- 오늘 한 일
  + 만족도 조사 : 만족도 조사 데이터 수집 및 전처리 시작.
  + PPT : PPT 전체적인 틀 잡기, 마무리된 내용 정리 및 후에 수정을 위한 기초 작성, 피드백 수용. 
  + 성수기 : 2022년 사후조사 시각화.
  + streamlit : 파일 데이터 streamlit에 올려두기,  월간보고서 데이터 연동하여 결과 노출시키기.
  + 물가 : 가설 설정 완료 및 분산분석 해석, 회귀분석 데이터 수집 및 전처리, 회귀분석 시작.

- 오늘 못한 일
  + PPT : 시각화를 어떻게 사용할 것인가, 리뷰 데이터 관련 아웃풋을 어떻게 사용할것인가에 대해. 
  + 성수기 : 2018-2021 데이터 전처리 마무리.
  + streamlit : 처리 완료된 나머지 데이터 연동하여 결과 노출시키기.
  + 물가 : 회귀분석 마무리.

- 내일 할 일
  + 만족도 조사 : 데이터 전처리 완료, 요인분석 시작.
  + PPT : 비어있는 내용 작성, 내용 관련 토의.
  + 성수기 : 2018-2021 데이터 시각화.
  + streamlit : 처리 완료된 나머지 데이터 연동하여 결과 노출시키기, 디자인 수정 및 추가 데이터 등록 반복.
  + 물가 : 회귀분석 마무리, 2022년 데이터 예측 시작하기.

[2023.09.20]

- 오늘 한 일
  + 만족도 조사 : 요인분석 데이터 전처리 완료 및 분석 시작.
  + PPT : 참고자료로 사용할 자료 수집 및 PPT 디자인 기초 설계, 내용 채우기. 
  + 성수기 : 2018-2021년 설문조사 전처리, 요인분석할 데이터 선정.
  + streamlit : 업로드 한 데이터의 전처리 코드 일부 형식에 맞게 정리하기, 일부 데이터 연동하여 노출시키기.
  + 물가 : 예측 시작 및 수정, 회귀 분석 마무리.

- 오늘 못한 일
  + PPT : 나머지 비어있는 내용 채우기. 
  + 성수기 : 전처리 내용 시각화 변경, 2022년 사전/사후조사 관련 요인분석 토의.
  + streamlit : 디자인 수정.

- 내일 할 일
  + 만족도 조사 : 분석 마무리.
  + PPT : 임의로 넣은 내용 토의, 변수 파트 채우기.
  + 성수기 : 2022년 사전사후조사 요인분석 시각화 재작업, 2022년 사전/사후조사 관련 요인분석 회의.
  + streamlit : 처리 완료된 나머지 데이터 연동하여 결과 노출시키기, 디자인 수정 및 추가 데이터 등록 반복.
  + 물가 : 예측 마무리 및 예측 결과 기반 시각화 시작.

- **Trouble-shooting**
  + 물가 부분의 데이터 프레임 병합과정에서 자잘한 오류 발생.
    + 해결방법을 찾아 해결함.

[2023.09.21]

- 오늘 한 일
  + 만족도 조사 : 정보습득경로 데이터 시각화, 불만족점 군집분석, 전국, 제주 물가 데이터 수집 및 가공을 통한 물가 비교 데이터 제작.
  + PPT : PPT 비어있는 내용 채우기 및 내용에 관한 피드백 회의. 
  + 성수기 : 요인 분석 관련 자료찾기 및 코드 연습.
  + streamlit : 업로드 한 데이터의 전처리 코드 일부 형식에 맞게 정리하기, 일부 데이터 연동하여 노출시키기.
  + 물가 : 예측을 위한 2022년도 관련 기틀잡기.

- 오늘 못한 일
  + PPT : 변수파트 작성 및 분석결과, 개선점 내용 채우기. 
  + 성수기 : 데이터 재검토 후 가설 재설정, 통계분석.
  + streamlit : 디자인 수정.
  + 물가 : 예측 마무리.

- 내일 할 일
  + 만족도 조사 : 여행경비 만족도 요인분석 완료.
  + PPT : 피드백 받은 내용들 추가수정 및 검수 전 내용 총 정리.
  + 성수기 : 가설 요인 분석후 시각화.
  + streamlit : 처리 완료된 나머지 데이터 연동하여 결과 노출시키기, 디자인 수정 및 추가 데이터 등록 반복.
  + 물가 : 예측 마무리 및 예측 결과 기반 시각화 완료.

[2023.09.22]

- 오늘 한 일
  + 만족도 조사 : 가설 검정 해석 및 최종 마무리.
  + PPT : PPT 비어있는 내용 채우기 및 내용에 관한 피드백 회의. 
  + 성수기 : 요인 분석 진행 방향 회의.
  + streamlit : 업로드 한 데이터의 전처리 코드 일부 형식에 맞게 정리하기, 일부 데이터 연동하여 노출시키기.
  + 물가 : 선형 회귀 모델 예측 완료 및 랜덤포레스트 진행 회의.

- 오늘 못한 일
  + PPT : 변수파트 작성 및 분석결과, 개선점 내용 채우기. 
  + 성수기 : 데이터 재검토 후 가설 재설정, 통계분석.
  + streamlit : 디자인 수정.
  + 물가 : 예측 마무리.

- 내일 할 일
  + 만족도 조사 : 여행경비 만족도 요인분석 완료.
  + PPT : 피드백 받은 내용들 추가수정 및 검수 전 내용 총 정리.
  + 성수기 : 가설 요인 분석후 시각화.
  + streamlit : 처리 완료된 나머지 데이터 연동하여 결과 노출시키기, 디자인 수정 및 추가 데이터 등록 반복.
  + 물가 : 예측 마무리 및 예측 결과 기반 시각화 완료.

[2023.09.24]

- 오늘 한 일
  + 물가 : 랜덤포레스트 삭제 및 2022년 데이터 결측치 평균대체법으로 확정 후 최종 마무리, 예측기반 시각화.
  + 성수기 : t 검정으로 변경 및 완료.

[2023.09.25]

- 오늘 한 일
  + 모든 변수 파트 : 데이터 정의서, 부족한 부분 보충.
  + PPT : 전반적인 틀 갈아엎음 + 내용 보강.
  + streamlit : 최종 배포본을 위한 마무리.

- 내일 할 일
  + 발표 전 최종 확인 및 발표.

 ## 최종 발표 PPT 
https://github.com/haeunkim48/Jeju_tourism_project-/blob/main/4%EC%A1%B0%20%EB%B0%9C%ED%91%9C%EC%9E%90%EB%A3%8C.pdf

 ## 프로젝트 기획안 
 https://github.com/haeunkim48/Jeju_tourism_project-/blob/main/%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%20%EA%B8%B0%ED%9A%8D%EC%95%88.docx.pdf
