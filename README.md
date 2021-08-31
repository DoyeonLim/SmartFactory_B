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
1. XGBoost
2. SVM
3. RandomForest
4. DecisionTree
5. [Logistic Regression](https://github.com/CUAI-CAU/SmartFactory_B/tree/main/model/Logistic%20Regression)

## 데이터 평가
1. F1_score
2. Recall(재현율)
3. Precision(정밀도)

![image](https://user-images.githubusercontent.com/64139953/131427377-2f1b119d-caf2-47ee-a864-a547c297a39a.png)

## 결론
- 2가지로 진행한 방법에 따른 결과 추이가 보이지 않음
- GridSearchCV로 하이퍼 파라미터 조정을 통해 예측성능이 향상됨

➜ **최종적으로, 전처리 방법2를 적용한 뒤 GridSearchCV로 교차검증을 하고 SVM 알고리즘으로 학습시킨 모델이 가장 좋은 예측 성능을 보였다.**










