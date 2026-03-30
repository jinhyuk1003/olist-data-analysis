# 🛒 Brazilian E-Commerce by Olist — 데이터 분석 & 배송 지연 예측 프로젝트

브라질 전자상거래 플랫폼 Olist의 실제 거래 데이터를 활용하여 탐색적 데이터 분석(EDA) 및 시각화를 수행하고, 머신러닝을 통해 배송 지연 여부를 예측하는 end-to-end 데이터 분석 프로젝트입니다.

<br />

## 📍 Business Problem

- 배송이 늦어질수록 고객 만족도와 리뷰 점수가 하락합니다.
- 불만족 고객은 재구매를 포기하고 이탈할 가능성이 높아집니다.
- 결과적으로 전체 매출과 브랜드 평판에 부정적인 영향을 미칩니다.

<br />

## 📂 Datasets

[Kaggle — Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

| 파일명                                  | 설명                              |
| --------------------------------------- | --------------------------------- |
| `olist_orders_dataset.csv`              | 주문 정보 및 배송 일정            |
| `olist_order_items_dataset.csv`         | 주문 내 상품 및 배송비            |
| `olist_order_payments_dataset.csv`      | 결제 방법 및 금액                 |
| `olist_order_reviews_dataset.csv`       | 고객 리뷰 점수 및 응답 시간       |
| `olist_customers_dataset.csv`           | 고객 지역 정보                    |
| `olist_sellers_dataset.csv`             | 판매자 지역 정보                  |
| `olist_products_dataset.csv`            | 상품 카테고리 및 물리적 속성      |
| `olist_geolocation_dataset.csv`         | 우편번호 기반 지리 정보           |
| `product_category_name_translation.csv` | 카테고리명 포르투갈어 → 영어 번역 |

<br />

## 🔄 Workflow

```
데이터 로드 → 데이터 정제 → 피처 엔지니어링 → 데이터셋 병합
     → EDA (고객 / 리뷰 / 시간 / 지역) → 예측 모델링
```

<br />

## 🚀 Run in Colab

- [EDA Notebook](https://colab.research.google.com/drive/1xiTuWnmB93myn9bMGhRRQ0mumnMdIRUn)
- [Modeling Notebook](https://colab.research.google.com/drive/109LA9T-bgRrdi-qlRezW9WxP4afgPnd9)

<br />

## 🔎 Exploratory Data Anaylsis

#### 1. 고객 분석

- 신규 vs 재구매 고객 비율: 약 96.88%가 첫 구매 고객
- 신규 고객이 전체 매출의 대부분을 차지하며, 재구매율 향상이 핵심 과제

#### 2. 리뷰 분석

- 고객의 약 80%가 4점 이상의 긍정적 리뷰를 남김
- 배송 지연 주문의 리뷰 평균 점수가 정시 배송 대비 유의미하게 낮음

#### 3. 지역 분석

- 상파울루(SP) 판매자와 동남부 고객 간 배송 지연이 가장 빈번
- 거래량 자체가 많아 절대적 지연 건수도 높음
- 특정 판매자-고객 주 조합에서 지연이 집중되는 패턴 확인

#### 4. 시간대별 분석

- 2017년 11월에 주문량이 최고조에 달함
- 2018년 3월에 배송 지연이 가장 많이 발생
- 화요일에 주문량과 지연 건수가 가장 많아 주 초반 물류 부하 집중

<br />

## 🤖 Machine Learning

배송 지연 여부(`is_late`)를 이진 분류로 예측합니다.

- 목표(Target): is_late (배송 지연 여부, 0/1)
- 문제 유형: Binary Classification
- 목적: 주문 생성 시점에 배송 지연 위험을 사전에 탐지하여 운영 의사결정에 활용

<br />

## 💡 비즈니스 인사이트

| 분석 영역 | 인사이트                                                           |
| --------- | ------------------------------------------------------------------ |
| 고객      | 재구매율(3.12%)이 매우 낮아 고객 유지 전략 강화 필요               |
| 리뷰      | 배송 지연은 리뷰 점수를 직접적으로 낮추는 핵심 변수                |
| 시간      | 화요일·주 초반에 물류 운영 자원 집중 필요                          |
| 지역      | SP 중심의 물류 허브 최적화 및 지연 루트 모니터링 필요              |
| 예측      | 상품 카테고리, 가격, 판매자/고객 지역이 배송 지연의 주요 예측 변수 |

<br />

## 👥 Team

- 지가은 (@gaeunji)

- 최수민 (@chsumin0316-oss)

- 홍채연 (@CYHong61)
