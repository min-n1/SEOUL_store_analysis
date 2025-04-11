## 서울시 소상공인을 위한 상권분석 서비스

### 프로젝트 기간
2025.02.25 ~ 2025.04.02

### 참여자
기솔아, 김경민, 이지홍, 이진우

### 프로젝트 소개 

2024년 기준, 서울시 자영업 폐업률은 125%를 기록하며 역대 최고치를 갱신했습니다. 이는 창업보다 폐업이 더 많은, 극심한 창업 리스크 시대를 반영하는 수치입니다.
과포화된 업종 구조와 경기 침체로 인해 소상공인의 생존율이 급감하고 있으며, 특히 예비 창업자들은 경험 부족과 정보 비대칭으로 인해 창업 자체를 망설이고 있는 실정입니다.

이에 따라 본 프로젝트는,
상권 분석 → 예상 매출 및 임대료 예측 → 매물 추천까지,
창업의 전 과정을 데이터 기반으로 지원하는 통합 창업 의사결정 지원 서비스를 제안합니다.

- '묻지마 창업'을 방지하기 위해 합리적인 의사결정 필요
- 상권분석과 적정 임대료 및 매출 데이터 정보 필요
- 사업 운영 시 발생할 수 있는 리스크 사전 인지 및 대비 가능
- 개인의 사업 계획에 맞는 맞춤형 매물 추천으로 안정적인 자금 계획 수립 지원

### 폴더 구조

### 기술 스택


### 데이터 소개

공공 및 민간에서 수집한 다양한 데이터를 활용하여 상권 분석, 매출 예측, 임대료 분석 등의 기능을 구현하였습니다.

### 🏙️ 인구 및 생활 기반 데이터  
**출처: 서울 열린데이터 광장**
- 길 단위 인구 (19,794 × 27)  
- 상주 인구 (19,576 × 29)  
- 직장 인구 (19,476 × 26)  
- 아파트 정보 (17,623 × 20)  
- 집객 시설 수 (18,936 × 25)  

### 💳 상권 및 소비 데이터  
**출처: 서울 열린데이터 광장**
- 매출 데이터 (249,331 × 55)  
- 소득 소비 데이터 (19,572 × 17)  
- 상권 변화 지표 (19,800 × 11)  
- 점포 데이터 (912,939 × 14)  

### 🏢 부동산/임대 관련 데이터  
**출처: 직방, 공공데이터포털**
- 상가 매물 데이터 (134,411개)  
- 행정동별 임대료 (1,231 × 10)  

### 데이터 전처리


### 주요 기능

1) 상권 매출 예측을 위한 머신러닝 모델 개발
2) 희망 매출/임대료를 기반으로 한 개인화 입지 추천
3) 생존률 예측 및 경쟁력 분석
