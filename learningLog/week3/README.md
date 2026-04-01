# 📚 3주차 TIL (Today I Learned)

### 1. 오늘 배운 개념 / 주제
  - 데이터 전처리(Preprocessing) 전체 흐름
    - EDA (탐색적 데이터 분석)
    - 결측치 처리
    - 이상치 처리
    - 인코딩
    - 스케일링
  - 머신러닝 모델 학습 과정
    - Train/Test Split
    - 모델 학습 및 평가
    - 모델 성능 비교
  - 대표적인 분류 모델 실습
    - KNN (K-Nearest Neighbors)
    - Neural Network (MLP)
    - Random Forest

---

### 2. 핵심 내용 요약

  1. 데이터 전처리 파이프라인
     - EDA
       - `info()`, `describe()`를 통해 데이터 구조 및 통계 확인
       - `isnull().sum()`으로 결측치 여부 확인
     - 결측치 처리
       - 수치형 → 평균/중앙값으로 대체
       - 범주형 → 최빈값으로 대체
       - 이번 데이터는 NaN 기준 결측치는 존재하지 않음
     - 이상치 처리
       - IQR 방식 사용
       - Q1, Q3 기준으로 범위 밖 데이터 제거
     - 인코딩
       - 문자열 컬럼 확인 후 One-hot encoding 수행
       - 이번 데이터는 모든 변수가 수치형 → 인코딩 생략
     - 스케일링
       - `StandardScaler` 사용
       - KNN, Neural Network는 거리 기반이므로 필수 적용
       - Random Forest는 스케일링 영향 거의 없음

  2. 데이터 분할 (Train/Test Split)
     - 데이터를 학습용과 테스트용으로 분리
     - 일반적으로 8:2 비율 사용
     - `stratify=y` 옵션으로 클래스 비율 유지

  3. 모델 학습 및 비교
     - KNN
       - 가까운 이웃 데이터를 기반으로 예측
       - k값에 따라 성능 변화
     - Neural Network
       - 은닉층을 통해 복잡한 패턴 학습
       - `(100, 50)` 구조 사용
     - Random Forest
       - 여러 개의 결정 트리를 결합한 앙상블 모델
       - 비선형 데이터에 강함

  4. 모델 성능 비교
     - 각 모델의 정확도를 계산하여 비교
     - 딕셔너리를 활용해 결과 정리
     - `max()`를 통해 최고 성능 모델 자동 선택

---

### 3. 실습 / 과제 결과물


for model, acc in results.items():
    print(f"{model}: {acc:.4f}")

best_model = max(results, key=results.get)
print(f"최고 성능 모델: {best_model}")
