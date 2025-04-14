## 서울시 소상공인을 위한 상권분석 서비스

### 📅 프로젝트 기간
- 2025.02.25 ~ 2025.04.02 (약 25일)

### 👥 참여자 및 역할

| **😊 김경민 (팀장)**                                   | **😁 기솔아 (기획자)**                                 |
|----------------------------------------------------|----------------------------------------------------|
| - 데이터 분석 정의서 작성                          | - 프로젝트 기획서 작성                             |
| - 데이터 수집 (직방 웹사이트 크롤링)               | - 시장조사 및 사용자 리서치                        |
| - 데이터 전처리 (이상치 처리, 스케일링)            | - 화면 UI/UX 기획 (IA, 와이어프레임, 스트림릿)     |
| - Streamlit 페이지 제작 (매출 예측, 매물 추천)     |  - Streamlit 페이지 제작 (각 페이지 기초 화면)                                                  |
| - Machine Learning을 활용한 매출 예측              |    - 발표 자료 제작 보완 (PPT, 시연 영상)              |
| &nbsp;&nbsp;&nbsp;└ 회귀분석: `RandomForest`, `XGBOOST` |                   |
| &nbsp;&nbsp;&nbsp;└ 군집분석: `K-Means`                 |                                                    |
| &nbsp;&nbsp;&nbsp;└ 시계열분석: `GRU`, `LSTM`, `DEEPAR+` |                                                    |


| **😘 이지홍 (데이터 분석)**                            | **🤔 이진우 (데이터 분석)**                            |
|----------------------------------------------------|----------------------------------------------------|
| - 프로젝트 기획서 작성                             | - 데이터 분석 정의서 작성                          |
| - 데이터 수집 (매출 예측 공공데이터)               | - 데이터 전처리 (축소 및 통합)                     |
| - Advanced RAG 구현 (`Rerank`, `MMR`)                     | - Fine-tuning (`GPT-4o-mini`, `Gemma3_12b`)            |
| - Streamlit 페이지 제작 (100일 생존 확률)&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;                            | - Streamlit 구조 설계 (navigation, session)        |
| - 발표 자료 제작 및 발표 (PPT)        | - Streamlit 페이지 제작 (Home, 상권분석) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;          |

<br>

### 🧭 서비스 흐름도
![image](https://github.com/user-attachments/assets/dcfb4efd-54e8-47df-89fd-bff63c57289d)

<br>

### 1. 프로젝트 배경 

&nbsp;  2024년 기준, 서울시 자영업 폐업률은 125%를 기록하며 역대 최고치를 갱신했습니다. 이는 창업보다 폐업이 더 많은, 극심한 창업 리스크 시대를 반영하는 수치입니다.
과포화된 업종 구조와 경기 침체로 인해 소상공인의 생존율이 급감하고 있으며, 특히 예비 창업자들은 경험 부족과 정보 비대칭으로 인해 창업 자체를 망설이고 있는 실정입니다.

> - '묻지마 창업'을 방지하기 위해 합리적인 의사결정 필요
> - 상권분석과 적정 임대료 및 매출 데이터 정보 필요
> - 사업 운영 시 발생할 수 있는 리스크 사전 인지 및 대비 가능
> - 개인의 사업 계획에 맞는 맞춤형 매물 추천으로 안정적인 자금 계획 수립 지원

<br>

### 2. 기대효과 
#### &nbsp; 1) 데이터 기반 창업 의사결정 확산
- 직관과 감에 의존한 창업 방식에서 벗어나, 정량 분석과 AI 예측에 기반한 합리적 창업 전략 수립 가능
#### &nbsp; 2) 지역 경제 활성화 및 상권 균형 발전 기여
- 특정 인기 상권으로의 쏠림을 방지하고, 유휴 상권에 대한 데이터 기반 매물 추천을 통해 지역별 균형 있는 상권 개발 유도
#### &nbsp; 3) 프롭테크 산업 연계 확대
- AI 기반의 매물 추천 서비스는 프롭테크 기업과의 제휴 및 확장 비즈니스 모델 창출 가능성 보유

<br>


### 3. 데이터 소개

&nbsp; 프로젝트에는 공공 데이터 포털, 서울 열린 데이터 광장, 직방의 데이터가 활용 되었습니다.
| 공공 데이터 포털 | 서울 열린데이터 광장 | 직방 |
|:--------------:|:------------------:|:---------:|
| <img src="https://www.gwff.kr/template/resources/images/cont/site_img_01.png" alt="공공 데이터 포털" width="230"/> | <img src="https://data.seoul.go.kr/resources/img/common/logo.png" alt="서울 열린데이터광장" width="200"/> | <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTMRFuKiLDgd9dVp0eMn_dSyDm9z2h3WFqU6g&s" alt="직방" width="230"/> |


#### &nbsp; 1) 👫 인구 및 생활 기반 데이터 (**서울 열린데이터 광장**)
```
- 길 단위 인구 (19,794 rows × 27 columns)
- 상주 인구 (19,576 rows × 29 columns)
- 직장 인구 (19,476 rows × 26 columns)
- 아파트 정보 (17,623 rows × 20 columns)
- 집객 시설 수 (18,936 rows × 25 columns)
- 상권 영역 데이터(21,675 rows × 6 columns)
```

#### &nbsp; 2) 💳 상권 및 소비 데이터  (**서울 열린데이터 광장**)
```
- 매출 데이터 (249,331 rows × 55 columns)
- 소득 소비 데이터 (19,572 rows × 17 columns)
- 상권 변화 지표 (19,800 rows × 11 columns)
- 점포 데이터 (912,939 rows × 14 columns)
```
#### &nbsp; 3) 🏢 부동산/임대 관련 데이터  (**직방, 공공데이터포털**)
```
- 상가 매물 데이터 (134,411개)  
- 행정동별 임대료 (1,231 rows × 10 columns) 
```
#### &nbsp; 4) ❓ 상가 매물 Q&A 데이터 (자체 제작)
```
- 서울시 상가 매물에 대한 질문, 답변 데이터 (110 rows x 2 columns)
```
#### &nbsp; 5) Streamlit 폴더 구조
```
📁 Streamlit
 ├─ app.py
 ├─ state.py
 │ 
 ├─ 📁 page
 │   ├─ commercial_analysis.py
 │   ├─ home.py
 │   ├─ loan.py
 │   └─ location.py
 │      
 ├─ 📁 model
 │   ├─ deepar_model_4.pkl
 │   ├─ scaler_X.pkl
 │   └─ scaler_y.pkl
 │ 
 ├─ 📁 chroma_db3
 │   ├─ chroma.sqlite3
 │   ├─ 📁 0d585fd0-b6af-4c08-af2b-a7719d61ce99
 │   └─ 📁 2781d1b3-d913-47b4-a651-05687acb1bbe
 │          
 ├─ 📁 data
 │   ├─ group_average_weights_상권_라벨.csv
 │   ├─ group_average_weights_서비스_라벨.csv
 │   ├─ group_average_weights_행정동_라벨.csv
 │   ├─ raw_data.csv
 │   └─ ref_data.csv
 │      
 ├─ 📁 img
 │   ├─ il_best.svg
 │   ├─ il_start.svg
 │   ├─ image.jpg
 │   ├─ llogo.png
 │   ├─ main_img.jpg
 │   ├─ newmoonlogo.png
 │   ├─ NEWMOON_LOGO.png
 │   ├─ slogo.png
 │   └─ 상권분석.png
 │      
 └─ 📁 util
     ├─ creata_map.py
     └─ popup.py
```


### 4. 데이터 전처리

#### &nbsp; 1) 상권 분석 데이터 통합 (229,415 rows × 178 columns)
##### &emsp; ① 데이터별 2024년 자료가 상이하여 2021년 1분기 ~ 2023년 4분기 까지의 자료만 필터링)     
##### &emsp; ② 인구 통계 데이터(상주인구, 유동인구, 집객시설 등), 상권별 매출 데이터, 점포 데이터를 순차적으로 merge    
##### &emsp; ③ merge 과정에서 메모리 부족으로 행정동, 상권, 업종 카테고리 라벨 인코딩 진행 후 merge 
##### &emsp; ④ 라벨 인코딩 과정에서 생성된 라벨 참조 테이블에 영역 데이터의 상권별 좌표(위도, 경도) merge

<br>

#### &nbsp; 2) 상권 분석 데이터 이상치 처리, 스케일링  (221,301 rows x 178 columns) 
##### &emsp; ① 상권 라벨이 126인 행 제거 
- 동일한 행정동명('신사동')을 갖는 ‘강남구 신사동’과 ‘관악구 신사동’ 중, 데이터 해석 혼선을 방지하기 위해 ‘관악구 신사동’에 해당하는 라벨 126번을 제거
##### &emsp; ② 상권 라벨과 서비스 라벨별 당월_매출_금액 이상치 분포 확인
- 특정 조합에서 비정상적으로 높은 이상치 발견 예) 상권 262번 & 서비스 64번, 상권 1070번 & 서비스 59번
##### &emsp; ③ 상권 라벨과 서비스 라벨의 조합별 99% 백분위수 값 계산
##### &emsp; ④ 확인된 높은 이상치를 가지는 두 조합에 대해, 99% 백분위수 값을 초과하는 경우 해당 값으로 대체
##### &emsp; ⑤ 전체 서비스 라벨 단위로 평균 ± 2 × 표준편차 범위 설정
- 각 서비스 라벨에 대해 적정 매출 범위를 설정
- 위에서 조정한 두 조합을 제외한 나머지 조합에 한해 이 범위를 벗어나는 이상치는 제거
##### &emsp; ⑥ 적정 범위를 벗어나는 이상치 제거 (제거 후 평균 9.5억 → 6억 축소)      
##### &emsp; ⑦ 매출 데이터의 분포를 안정화하기 위해 np.log1p()를 사용한 로그 스케일링 적용
##### &emsp; ⑧ 분석 및 모델 학습을 위해 전체 독립변수에 MinMaxScaler 적용하여 정규화 진행
##### &emsp; ⑨ KMeans 클러스터링으로 상권·서비스 특성군 생성
- 상권 라벨 1300여 개 → 500개 클러스터, 서비스 라벨 99개 → 60개 클러스터로 축소
- 이후 분석/모델에서 유사한 지역·업종군 파악에 활용

<br>

### 5. 주요 기능
#### &nbsp; 1) 상권 매출 예측 모델 

<img width="1155" alt="image" src="https://github.com/user-attachments/assets/3f50fab2-4f89-40b1-9901-2850a04e7eaa" />   

##### &emsp; ① 기능 : 사용자가 선택한 상권 및 업종 정보를 바탕으로, 해당 조건에 맞는 예상 매출을 예측  
##### &emsp; ② 모델링    
| 항목     | 사용 모델                               |
|---------------|-------------------------------------------|
| 회귀 분석     | `XGBoostClassifier`, `RandomForestClassifier` |
| 군집 분석     | `K-Means`                                      |
| 시계열 분석   | `GRU`, `LSTM`, `DeepAR+`                   |     
   

##### &emsp; ③ 특이사항   
> - 공공데이터 기반의 시계열 분석 모델을 활용해 정량적이고 신뢰도 높은 예측 가능   
> - 동 단위 상권의 소비 성향과 성장 흐름을 고려하여 파악한 서울시 각 상권별 트렌드를 이용하여 매출 예측에 차별화 적용   
> - 업종별 특성(예: 카페 vs 식당)을 고려하여 세분화된 매출 예측 제공   

##### &emsp; ④ 모델 검증     
&emsp;&emsp; **a) LSTM**
> -

<br>

&emsp;&emsp; **b) GRU**
> -

<br>

&emsp;&emsp; **c) DeepAR+**
> - 데이터 분할: 훈련 데이터, 검증 데이터, 테스트 데이터를 8:1:1 비율로 분할
> - 모델 정의: DeepAR 스타일의 LSTM 기반 시계열 모델 정의
> - 모델 훈련:`X_train`, `y_train`으로 100 에포크 동안 훈련, 검증 데이터셋으로 검증 진행
>   
>   ```python
>   model.fit(X_train, y_train, epochs=100, batch_size=128, validation_data=(X_val, y_val))
>   ```
> - 모델 컴파일: optimizer='adam', loss='mean_squared_error'
> - 예측: 훈련된 모델을 이용하여 X_test로 예측 수행
> - 역변환: 예측 결과를 원래 스케일로 복원
> - 평가 지표: RMSE, MAE, R² 계산
>   - RMSE: 0.1188707
>   - MAE: 0.0893809
>   - R²: 0.9993

<br>

&emsp;&emsp; **(모델 검증에 사용된 주요 지표)**
- RMSE (Root Mean Squared Error): 예측 값과 실제 값 간의 차이를 제곱한 후 평균을 취한 뒤 루트를 씌운 값으로, 예측 정확도를 평가.
- MAE (Mean Absolute Error): 예측 값과 실제 값 간의 절대적인 차이의 평균으로, 오차가 얼마나 큰지 직관적으로 파악 가능.
- R² (Coefficient of Determination): 모델의 설명력을 나타내는 지표로, 예측 값이 실제 값을 얼마나 잘 설명하는지를 평가.

<br>

#### &nbsp; 2) 맞춤형 매물 추천 모델  

<img width="1155" alt="image" src="https://github.com/user-attachments/assets/87635fea-9ec2-419f-be36-dac97fc5f8a2" />   


💛💛 매물추천 지도가 깜빡거려서 ... 경민님 캡쳐 plz    

##### &emsp; ① 기능 : 유저의 자연어 입력(예: “월세 300만 원 이하, 쌍문동, 카페”)을 이해하고 조건에 맞는 매물 정보와 추천 이유 제공    
##### &emsp; ② 모델링    
 | **항목** | **설명** |
 |------|------|
 | 파인튜닝(Fine-tuning) | `GPT-4o-mini`, `Gemma3_12b` 모델을 자체 Q&A 데이터(108개)로 미세조정 |
 | Retrieval-Augmented Generation | 13만 상가 매물 데이터를 `ChromaDB`에 저장하여 답변 정확도 개선 |
 | 검색 최적화 | `MMR(Maximal Marginal Relevance)` 기반 유사 매물 필터링 |
 | 랭킹 개선 | `Cohere Rerank`를 통해 의미 기반 재정렬 및 중복 제거 |  
 | 출력 형식 개선 | `Few-shot` 기법으로 자연스럽고 일관된 답변 유도 |  

##### &emsp; ③ 특이사항       
> - 추천 이유가 일반적이거나 반복되는 문제 발생       
> - 프롬프트 내부에 "추천 이유는 \*\*매물 설명**을 기반으로 작성하세요."와 같은 명시적 지시 문장을 추가하여,    
> 모델이 특정 필드의 정보를 중점적으로 활용하도록 유도       
> - 그 결과, 추천 이유가 매물의 실제 특징(예: ‘넓은 실내’, ‘유동 인구 많은 위치’)을 반영하게 되어 설명력 향상
    
##### &emsp; ④ 모델 검증
&emsp;&emsp; **a) GPT-4o-mini**
> - 팀원 평가(10점) : 위치, 월세, 보증금, 권리금, 면적, 층수(각 1점) / 추천 이유(4점)
> - [MT-Bench](https://huggingface.co/spaces/lmsys/mt-bench)의 Prompt를 차용하여 GPT-4o모델이 평가
> - 평가 결과 두 모델의 성능이 크게 다르지 않음을 검증   

| 검증 주체 | GPT-4o-mini | GPT-4o | 무승부 |
|:---:|:---:|:---:|:---:|
| 팀원1 | 4 | 5 | 1 |
| 팀원2 | 5 | 5 | 0 |
| 팀원3 | 6 | 3 | 1 |
| 팀원4 | 4 | 4 | 2 |
| MT-Bench | 20 | 15 | 5 |
| **합계** | **39** | **32** | **9** |

<br>

&emsp;&emsp; **b) Gemma3_12b**
> - 답변 시간 지연 및 리소스 문제로 별도 검증을 진행하지 않음
> - 하지만 LoRA를 이용한 적은 파라미터(0.26%) 학습만으로도 좋은 답변 성능 확인

<img width="700" alt="image" src="https://github.com/user-attachments/assets/b3e52118-6c7d-47d4-82d2-0ff2bc0ea147"/>

<br>
<br>

#### &nbsp;3) 상권 분석 서비스
![image](https://github.com/user-attachments/assets/95a7473c-7a7d-40cc-ad17-fba242abe2d9)
##### &emsp; ① 기능 : 유동인구, 평균 매출, 폐업률, 개업률, 평균 임대료, 업종별 임대료 정보 제공
##### &emsp; ② 모델링
> - Streamlit의 st_folium를 활용하여 실시간 상권 지도 및 정보 제공
##### &emsp; ③ 특이사항 
> - 전체 지도의 marker를 찍는데 많은 시간 소요
> - folium에 전달되는 자료 구조를 dict로 변경하여 소요시간 절감

<!-- 이미지
<img width="1380" alt="image" src="https://github.com/user-attachments/assets/12f34678-4e47-4e07-9537-89cde76f08d7" />
<img width="1371" alt="image" src="https://github.com/user-attachments/assets/cbc77cdd-895b-4121-b005-5aff578ba323" />
<img width="1371" alt="image" src="https://github.com/user-attachments/assets/c9069109-55a8-4b7a-9af7-7139ef477dc2" />
-->

<br>

#### &nbsp;4) 100일 생존 확률 분석 서비스

<img width="1155" alt="image" src="https://github.com/user-attachments/assets/f7a84907-e6b4-4b4d-93b7-5553f74d6d30" />

##### &emsp; ① 기능 : 점포 생존 확률(매출 변동, 시각화) 예측 및 상권 경쟁력 분석
##### &emsp; ② 모델링
> - RandomForest의 Feature_importances를 기준으로 핵심지표 설계
> - 핵심지표를 이용하여 100일 생존 확률 예측 및 상권 경쟁력 분석     
##### &emsp; ③ 특이사항  
> - 생존 확률에 대한 신뢰성 검증 미비(추후 보완 예정)


<br>

### 6. 프로젝트 소회

