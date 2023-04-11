# Delivery-Predicting-System
## 개요

MIMIC-III 데이터를 사용해 중환자실에 입원한 심부전 환자들의 사망 여부 예측 프로젝트입니다.

## 데이터

원본 데이터는 MIMIC-III에서 가져와야하지만 프로젝트에서는 kaggle에 있는 정제된 데이터입니다.

## 과정

결측치와 이상치에 대해 분석을 진행하고 사망자와 생존자간에 차이점을 찾아냅니다. 환자들의 인구통계학적 특징, 중복이환, 활력 징후, 병리 수치에 대해서 분석했습니다. 단순 빈도 비교, T-test, 차원 축소 방법으로 유의미한 차이를 내는 특성들을 찾았습니다. 예측을 위해 통계적 방법이 아닌 기계학습 모델도 테스트했습니다. K근접 이웃, 로지스틱 회귀, LightGBM, 로지스틱 회귀와 LightGBM을 Soft Voting을 통해 합친 모델로 각각 학습 후 성능을 테스트했습니다. 가장 성능이 좋았던 Soft Voting 모델로 최종 학습 후 모델이 판단한 생존과 사망에 중요한 특성들을 나타냈습니다.

## 결과

이 과정을 통해 몇몇 특성들이 생존자와 사망자에 따라 다른 수치를 나타내며
중환자실에서 심부전 환자의 생존률을 높이기 위해서는 이 특성들을 유의해서 봐야 한다고 할 수 있습니다.
그 특성은 고령인 경우, 심방 세동이 있는 경우, 심박수가 증가하거나 호흡이 가빠지는 경우
임상 병리 검사를 했을 때 음이온 차나 락트산, 요소질소가 확연히 증가한 경우 입니다.
이러한 경우라면 앞으로의 변화를 더 유심히 살펴보면서 혈액 내 수치들의 변화를 빠르게 확인하기 위해
혈액 검사 빈도를 늘리는 방법도 고려할 수 있을 것입니다.

## 출력 예시
- 인구 통계학적 특성  
![image](https://user-images.githubusercontent.com/94027045/220046941-eea609a5-6588-4ece-997e-4b823042a1c8.png)

- 모델 예측 점수  
![image](https://user-images.githubusercontent.com/94027045/220046798-3515271d-b274-45e2-b829-cc07f091d434.png)

- 병리 수치에서 PDP 차트  
![image](https://user-images.githubusercontent.com/94027045/220046220-fe443145-3a1f-4885-bcb1-dc181ab0c472.png)
