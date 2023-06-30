# 머신러닝 앙상블 기반 농업인 우울군 분류에서의 특성 중요도 연구
2022.04 ~ 2022.11 (8개월)
## 📗 목차
  - 👨🏻‍💻 담당업무
  - ✍️ 서론
  - 📑 프로젝트 내용
    - 데이터 전처리
    - 모델링
    - 우울증의 주요 원인 분석
  - 🏆 결과 및 성과
  - 💡 Insight

## 👨🏻‍💻 담당업무
- 팀장 - 팀 프로젝트 진행 관리, 구성 기획 및 업무 분담, 발표
- 분석방법론 설계 및 검증
- EDA
- 데이터 전처리
- 모델링

## ✍️ 서론
- 농업 관련 인적 재해의 예방과 관리를 위한 실효성 있는 정책을 수립하기 위해 농촌진흥정 국립농업과학원에서 농업인의 업무상 질병 및 손상 조사를 진행한다.
- 위 조사에서 얻은 통계적 자료를 이용하여 **농업인의 우울증을 예측하고, 이와 관련된 주요 원인을 제거 및 예방**하고자 연구를 진행했다.

## 📑 프로젝트 내용
### 1. 데이터 전처리

- 예측 모델의 정확도를 높이기 위해, 데이터에서 우울도(정신 질환 관련)와 직접적으로 관련된 문항들을 제거
- One-Hot Encoding을 진행할 문항과 진행하지 않은 문항을 분류한 뒤, 분류한 문항에 One-Hot Encoding을 진행
- 우울도와 직접적으로 관련된 문항들을 이용해 PHQ-9(우울증 자가진단 도구)를 사용해 PHQ-9 점수를 부여하여 target 열 설정
- 합산한 PHQ-9 점수가 10점 이상인 사람의 수(target=1)가 457명, 10점 미만인 사람의 수(target=0)가 9982명으로 데이터불균형이 있다고 판단 → target이 1인 사람 수에 맞춰 target이 0인 사람의 데이터를 랜덤하게 457개 추출하며 총 914의 케이스를 발췌하여 데이터 균형을 맞춤


### 2. 모델링

- 685개의 학습 데이터와 229개의 테스트 데이터를 사용하여 10개의 머신러닝(Random Forest, GradientBoost, XGBoost 등)과 교차검증을 사용하여 모델 학습 진행
- 정확도를 평가지표로 사용하여 정확도의 평균을 구하여 모델의 성능 확인
![image](https://github.com/DOYOON510/Farmer-depression-prediction/assets/129147977/18589a7d-c3d6-4e7e-8e5e-3bb2f0f57e7b)

- 학습을 진행한 머신러닝 모델 중 상위권에 포함되어 있는 5개의 모델을 선택해 Bayesian optimization 진행
![image](https://github.com/DOYOON510/Farmer-depression-prediction/assets/129147977/1c93a116-0764-4b01-8b21-7de282ade37e)

- Bayesian optimization를 진행해본 결과, 정확도가 가장 높은 XGBoost 모델을 최종 모델로 선정
![image](https://github.com/DOYOON510/Farmer-depression-prediction/assets/129147977/24d3c645-8999-4a76-a906-4381338c9115)


## 3. 우울증의 주요 원인 분석

- XGBoost 모델의 특성중요도를 이용하여 우울증에 영향을 미치는 주요 문항확인 후, 우울군과 비우울군에 해당되는 농업인 수 확인 및 비교
![image](https://github.com/DOYOON510/Farmer-depression-prediction/assets/129147977/28631982-1c82-40cd-b2ca-1f94e60ecf65)
![image](https://github.com/DOYOON510/Farmer-depression-prediction/assets/129147977/8a0ba7f1-476b-4984-a5ff-ac50942e06be)


## 🏆 결과 및 성과
- 교내 포스터발표 진행
- 농업인의 우울증에 영향을 미치는 주요 원인 확인 및 분석
- PHQ-9을 사용하여 농업인의 우울증 예측을 진행하는 머신러닝 모델 개발

## 💡 Insight
- 모델링을 진행하며 변수 선택 및 모델 선택의 중요성을 알게되었으며, 모델의 성능을 높이기 위해 고민해야할 요소가 무엇이 있는지 파악하였음
- Bayesian optimization을 사용하며 머신러닝의 하이퍼파라미터에 관한 이해 능력이 향상됨
