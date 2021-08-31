# SmartFactory_B : UCI-SECOM
[Paper](https://github.com/CUAI-CAU/SmartFactory_B/blob/main/Final%20Report/2021_%EC%BB%A8%ED%8D%BC%EB%9F%B0%EC%8A%A4_%EC%8A%A4%EB%A7%88%ED%8A%B8%ED%8C%A9%ED%86%A0%EB%A6%ACB%ED%8C%80.docx) | [PPT](https://github.com/CUAI-CAU/SmartFactory_B/blob/main/Final%20Report/2021_%EC%BB%A8%ED%8D%BC%EB%9F%B0%EC%8A%A4_%EC%8A%A4%EB%A7%88%ED%8A%B8%ED%8C%A9%ED%86%A0%EB%A6%ACB%ED%8C%80.pptx)
## Members
- **유찬재**(School of Mechanical Engineering, Chung-Ang University)
- **최연찬**(School of Mechanical Engineering, Chung-Ang University)
- **🙋‍♀️임도연**(School of Computer Science and Engineering, Chung-Ang University)

## 주제 
반도체 제조 과정에서의 수율 향상을 위한 이진 분류 모델 비교 분석

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

![image](https://user-images.githubusercontent.com/64139953/131492963-ae148f86-34dd-4ed7-b644-2e01a959ffbd.png)

![image](https://user-images.githubusercontent.com/64139953/131492995-b3549baa-05e8-413e-9c2e-fd4b35741487.png)

![image](https://user-images.githubusercontent.com/64139953/131493005-abe5b0d1-7cfe-4a4d-8f87-e7d47d21627a.png)



➜ **최종적으로, 전처리 방법2를 적용한 뒤 GridSearchCV로 교차검증을 하고 SVM 알고리즘으로 학습시킨 모델이 가장 좋은 예측 성능을 보였다.**










