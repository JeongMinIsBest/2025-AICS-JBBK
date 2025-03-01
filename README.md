# 2025 AICS Bloom AI Stock Model 📈

## 🏗 프로젝트 개요
이 프로젝트는 전북 전주시의 기온 및 강수량 데이터를 기반으로 KOSPI 상위 10개 종목의 주가 예측을 수행하는 실시간 예측 시스템을 구축하는 것을 목표로 합니다.
이를 위해 XGBoost 모델을 활용하여 학습을 진행하였으며, 실시간 데이터 수집 및 예측 시스템을 구현했습니다.

</br>

## 🛠 주요 기술 및 라이브러리
- 데이터 수집 : ```FinanceDataReader```, ```기상청 API```
- 데이터 전처리 및 분석 : ```pandas, numpy```, ```scikit-learn```
- 머신러닝 모델 : ```XGBoost```
- 시각화 : ```matplotlib```, ```seaborn```

</br>

## AI Model
### Data Processing
- 주식 데이터와 계절 데이터 병합
- 강수량 데이터의 결측치는 선형 보간법을 사용하여 보완

</br>

### Model Training
- 데이터 특성 상 

## Data 🧩
### Dataset

**1. 주식 데이터** (2024.01.01 - 2024.12.31 / KOSPI 기준 상위 10개 기업)
  - 일자
  - 기업명
  - 당일 시가 (주식 시장 열릴 때 가격)
  - 당일 고가 (장 중 최고 가격)
  - 당일 저가 (장 중 최저 가격)
  - 당일 종가 (장 마감 시 가격)
  - 당일 거래량 (해당 주식이 거래된 총 주식 수)
  - 전일 대비 가격 변화량 (종가 - 전일 종가)
  - 전일 대비 변화 비율 (가격 변화량 / 전일 종가 * 100)

![image](https://github.com/user-attachments/assets/14cf1762-0b54-4823-bfba-47b2f867be24)

</br>

**2. 계절 데이터** (2024.01.01 - 2024.12.31 / 전라북도 전주 기준)
   - 일 강수량 데이터
   - 일 평균 기온 데이터

### Raw Data
| 데이터명 | 기준 | 출처 | 링크 |
|:------:|:------:|:------:|:------:|
| 강수량 | 2024.01 - 2024.12 / 전북 전주시 | 기상청 기상자료개방포털 | https://data.kma.go.kr/stcs/grnd/grndRnList.do?pgmNo=69 |
| 기온 | 2024.01 - 2024.12 / 전북 전주시 | 기상청 기상자료개방포털 |  https://data.kma.go.kr/stcs/grnd/grndTaList.do?pgmNo=70 |
| KOSPI 상위 10개 종목 | 2024.01 - 2024.12 | KRX | FinanceDataReader |
