# SmartFactory_B : UCI-SECOM
## Members
- 유찬재(기계공학부)
- 최연찬(기계공학부)
- 임도연(소프트웨어학부)

## 주제 
반도체 제조과정에서의 수율 향상을 위한 이진 분류 모델 비교 분석

## 데이터
캐글(https://www.kaggle.com/paresh2047/uci-semcom) 에서 제공하는 데이터셋 이용

**데이터 특징**
- 고유치가 1인 열 존재
- Pass/Fail 데이터 비율이 고르지 않음
- 데이터 값의 편차가 큼

## 데이터 전처리
1. 결측값 처리
- 결측값이 900개가 넘는 열은 삭제 후 남은 결측값은 0으로 대체
- 결측값이 50%가 넘는 열과 고유치가 1인 열은 삭제 후 남은 결측값은 앞,뒤 행의 값으로 대체

2. 데이터 스케일링
- Oversampling(오버샘플링)
- StandardScalre(표준화)
- PCA(주성분 분석)

## 데이터 모델링
- [XGBoost](https://github.com/CUAI-CAU/SmartFactory_B/tree/main/model/XGBoost)
- [SVM](https://github.com/CUAI-CAU/SmartFactory_B/tree/main/model/SVM)
- [RandomForest](https://github.com/CUAI-CAU/SmartFactory_B/tree/main/model/RandomForest)
- [DecisionTree](https://github.com/CUAI-CAU/SmartFactory_B/tree/main/model/DecisionTree)
- [Logistic Regression](https://github.com/CUAI-CAU/SmartFactory_B/tree/main/model/Logistic%20Regression)
- (참고) [Linear Regression](https://github.com/CUAI-CAU/SmartFactory_B/tree/main/model/Linear%20Regression(%EC%B0%B8%EA%B3%A0))

## 데이터 평가
- F1_score
- Recall(재현율)
- Precision(정밀도)

![image](https://user-images.githubusercontent.com/64139953/131429624-e6533840-9dbe-4dbd-b7a0-805ad2721298.png)

## 결론
- 2가지로 진행한 데이터 전처리 방법에 따른 경향성이 보이지 않음
- GridSearchCV로 하이퍼 파라미터 조정을 통해 예측성능이 향상됨

![image](https://user-images.githubusercontent.com/64139953/131440956-aef32755-486c-427b-bda1-5726d3db821b.png)

![image](https://user-images.githubusercontent.com/64139953/131440967-09013489-53e0-47f0-8754-7df7c8600938.png)

![image](https://user-images.githubusercontent.com/64139953/131440980-5ac05c2b-6823-45d1-b030-e3612a655bc0.png)



➜ **최종적으로, 전처리 방법2를 적용한 뒤 GridSearchCV로 교차검증을 하고 SVM 알고리즘으로 학습시킨 모델이 가장 좋은 예측 성능을 보였다.**










