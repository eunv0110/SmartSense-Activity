# 📱 스마트폰 센서 기반 행동 인식 프로젝트

<div align="center">
  <img src="https://raw.githubusercontent.com/mdn/content/main/files/en-us/Web/API/Accelerometer/accelerometer.svg" width="400px" />
  <br><br>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" />
  <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" />
  <img src="https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" />
  <br><br>
  <p><i>KT AIVLE School AI 트랙 미니프로젝트 3차</i></p>
</div>

<br>

## 📋 프로젝트 개요

<div align="center">
  <h3><i>"스마트폰 센서 데이터를 활용한 인간 행동 인식(HAR) 모델 개발"</i></h3>
</div>

<br>

본 프로젝트는 스마트폰의 가속도계와 자이로스코프 센서 데이터를 활용하여 사용자의 행동을 자동으로 인식하는 모델을 개발하는 것을 목표로 합니다. 이러한 기술은 헬스케어, 운동 모니터링, 안전 관리 등 다양한 분야에 활용될 수 있습니다.

<br>

## ⏰ 프로젝트 기간
- 2025년 2월 28일 ~ 2025년 3월 2일 (3일간)

<br>

## 📝 문제 정의

```
❓ 스마트폰 센서 데이터(가속도계, 자이로스코프)를 통해 6가지 동작을 정확히 분류할 수 있는가?
```

<br>

### 행동 인식이 중요한 이유:

- 🔹 스마트 디바이스의 컨텍스트 인식 기능 강화
- 🔹 건강 모니터링 및 활동 추적 서비스 지원
- 🔹 사용자 맞춤형 서비스 제공을 위한 기초 기술
- 🔹 낙상 감지 등 안전 관련 응용 프로그램 개발 가능

<br>

## 📊 데이터 소개

<table>
  <tr>
    <th align="center" width="20%">분석 대상</th>
    <td>스마트폰 센서 기반 인간 행동 데이터</td>
  </tr>
  <tr>
    <th align="center">출처</th>
    <td>UCI Machine Learning Repository</td>
  </tr>
  <tr>
    <th align="center">데이터 구성</th>
    <td>
      <ul>
        <li>561개의 특성(feature)으로 구성된 데이터셋</li>
        <li>총 7,353개의 샘플(행)</li>
        <li>6개의 행동 클래스: STANDING, SITTING, LAYING, WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS</li>
      </ul>
    </td>
  </tr>
  <tr>
    <th align="center">측정 방법</th>
    <td>
      <ul>
        <li>30명의 피실험자가 허리에 착용한 스마트폰(Samsung Galaxy S II)을 통해 데이터 수집</li>
        <li>2.56초 window 단위로 데이터 샘플링, 50% 중첩(overlapping)</li>
        <li>다양한 통계적 특징(평균, 표준편차, 최대값 등) 추출</li>
      </ul>
    </td>
  </tr>
</table>

<br>

## 🛠️ 프로젝트 수행 단계

<div style="display: flex; justify-content: space-between;">
  <div style="width: 30%;">
    <h3>1️⃣ 탐색적 데이터 분석</h3>
    <ul>
      <li>데이터 기본 정보 확인</li>
      <li>특성 중요도 분석</li>
      <li>상위/하위 특성 KDE 시각화</li>
      <li>정적/동적 행동 그룹 분석</li>
      <li>센서 및 집계 방식별 중요도 분석</li>
    </ul>
  </div>
  <div style="width: 30%;">
    <h3>2️⃣ 기본 모델링</h3>
    <ul>
      <li>데이터 전처리 (스케일링, 인코딩)</li>
      <li>다양한 신경망 구조 실험
        <ul>
          <li>은닉층 없는 기본 모델</li>
          <li>다층 신경망 모델</li>
          <li>드롭아웃 적용 모델</li>
          <li>조기 종료(Early Stopping) 적용 모델</li>
        </ul>
      </li>
      <li>모델 성능 비교 및 평가</li>
    </ul>
  </div>
  <div style="width: 30%;">
    <h3>3️⃣ 단계별 모델링</h3>
    <ul>
      <li>계층적 모델 구성
        <ul>
          <li>1단계: 정적/동적 행동 분류</li>
          <li>2단계: 세부 행동 분류(각 그룹별)</li>
        </ul>
      </li>
      <li>모델 통합 파이프라인 구축</li>
      <li>테스트 데이터 예측 및 성능 평가</li>
    </ul>
  </div>
</div>

<br>

## 🧪 실험 결과

### 📊 변수 중요도 분석

<div align="center">
  <table>
    <tr>
      <th>분석 관점</th>
      <th>주요 특성</th>
      <th>관찰 결과</th>
    </tr>
    <tr>
      <td>6개 행동 구분</td>
      <td>
        <ul>
          <li>fBodyAcc-bandsEnergy()-1,8</li>
          <li>fBodyAccJerk-bandsEnergy()-1,24</li>
          <li>fBodyGyro-bandsEnergy()-1,24</li>
        </ul>
      </td>
      <td>
        <ul>
          <li>LAYING은 비교적 분류가 잘 됨</li>
          <li>다른 행동 간에는 구분이 상대적으로 어려움</li>
          <li>주파수 영역의 에너지 밴드 관련 특성이 중요함</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>정적/동적 행동 구분</td>
      <td>
        <ul>
          <li>tBodyGyro-mean()-Z</li>
          <li>tGravityAcc-mean()-X</li>
          <li>tBodyGyro-std()-Z</li>
        </ul>
      </td>
      <td>
        <ul>
          <li>소수의 특성만으로도 높은 정확도로 구분 가능</li>
          <li>중력 가속도와 자이로스코프 센서 데이터가 핵심적</li>
          <li>특성 상위/하위 분석에서 뚜렷한 그룹 구분 확인됨</li>
        </ul>
      </td>
    </tr>
  </table>
</div>

### 📈 기본 모델 성능 비교

<div align="center">
  <table>
    <tr>
      <th>모델</th>
      <th>Hidden Layer</th>
      <th>Dropout</th>
      <th>Early Stopping</th>
      <th>Accuracy</th>
      <th>Test</th>
    </tr>
    <tr>
      <td>model1</td>
      <td>-</td>
      <td>-</td>
      <td>-</td>
      <td>0.97 (0.954,0.975)</td>
      <td>0.955812</td>
    </tr>
    <tr>
      <td>model2</td>
      <td>64,32,16,8</td>
      <td>-</td>
      <td>-</td>
      <td>0.98 (0.969,0.986)</td>
      <td>0.959891</td>
    </tr>
    <tr>
      <td>model3</td>
      <td>64,32,16,8</td>
      <td>0.1</td>
      <td>-</td>
      <td>0.98 (0.970,0.986)</td>
      <td>0.951054</td>
    </tr>
    <tr>
      <td>model4</td>
      <td>64,32,16,8</td>
      <td>0.1</td>
      <td>min_delta=0.001, patience=5</td>
      <td>0.97 (0.961,0.980)</td>
      <td>0.941536</td>
    </tr>
    <tr>
      <td>model7</td>
      <td>64,32</td>
      <td>-</td>
      <td>-</td>
      <td><b>0.98 (0.971,0.987)</b></td>
      <td>0.961251</td>
    </tr>
  </table>
</div>

<br>

### 📈 계층적 모델 성능

<div align="center">
  <table>
    <tr>
      <th>단계</th>
      <th>모델</th>
      <th>정확도</th>
      <th>구성</th>
    </tr>
    <tr>
      <td>1단계</td>
      <td>정적/동적 행동 분류</td>
      <td><b>0.999</b></td>
      <td>Hidden Layer: 32, epoch: 50, learning rate: 0.001, sigmoid 활성화 함수</td>
    </tr>
    <tr>
      <td rowspan="2">2단계</td>
      <td>동적 행동 세부 분류</td>
      <td>0.99</td>
      <td>Hidden Layer: 64,32,16, epoch: 50, softmax 활성화 함수</td>
    </tr>
    <tr>
      <td>정적 행동 세부 분류</td>
      <td>0.96</td>
      <td>Hidden Layer: 512,128,32, epoch: 70, softmax 활성화 함수</td>
    </tr>
    <tr>
      <td>통합</td>
      <td>파이프라인 모델</td>
      <td>0.97</td>
      <td>1단계 + 2단계 모델을 결합한 파이프라인</td>
    </tr>
  </table>
</div>

<br>

## 🌟 계층적 모델링 접근법

우리 프로젝트의 핵심은 복잡한 다중 분류 문제를 더 단순한 하위 문제로 분해하는 계층적 접근법입니다:

<div align="center">
  <img src="https://github.com/user-attachments/assets/cccdf105-3884-4f42-85c9-4ab954777713" alt="계층적 모델링 접근법" width="600px">
</div>

<br>

1. **1단계 모델**: 정적 행동(0)과 동적 행동(1)을 구분 (정확도: 99.9%)
   - 정적 행동: STANDING, SITTING, LAYING
   - 동적 행동: WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS

2. **2-1단계 모델**: 정적 행동 내 세부 분류 (정확도: 96%)
   - STANDING, SITTING, LAYING 구분

3. **2-2단계 모델**: 동적 행동 내 세부 분류 (정확도: 99%)
   - WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS 구분

4. **통합 파이프라인**: 두 단계 모델을 결합하여 최종 예측 수행 (정확도: 97%)

<br>

## 💡 모델 선택과 최적화

<div style="display: flex; justify-content: space-between;">
  <div style="width: 48%; padding: 15px; border: 1px solid #ddd; border-radius: 8px; background-color: #f9f9f9;">
    <h3>🔍 최적 단일 모델</h3>
    <p><b>✓ model 7: Accuracy(정확도) : 0.98</b></p>
    <ul>
      <li>hidden layer 개수 2개</li>
      <li>Dropout, Early Stopping 미사용</li>
      <li>단순한 구조로 설정했을 때 가장 정확도가 높게 나옴</li>
    </ul>
  </div>
  <div style="width: 48%; padding: 15px; border: 1px solid #ddd; border-radius: 8px; background-color: #f9f9f9;">
    <h3>🔍 최적 계층적 모델</h3>
    <p><b>✓ 1단계 모델: Accuracy(정확도) : 0.999</b></p>
    <ul>
      <li>정적 행동과 동적 행동을 분류하는 모델</li>
      <li>매우 높은 정확도로 두 그룹 구분 가능</li>
      <li>단순한 구조로도 뛰어난 성능 달성</li>
    </ul>
  </div>
</div>

<br>

## 💡 결론 및 시사점

<div style="display: flex; justify-content: space-between;">
  <div style="width: 48%; padding: 15px; border: 1px solid #ddd; border-radius: 8px; background-color: #f9f9f9;">
    <h3>📝 주요 결론</h3>
    <ul>
      <li>계층적 모델링 접근법이 복잡한 분류 문제 해결에 효과적</li>
      <li>정적/동적 행동은 매우 높은 정확도(99.9%)로 구분 가능</li>
      <li>동적 행동 내 세부 분류(99%)가 정적 행동 내 세부 분류(96%)보다 더 정확함</li>
      <li>모델 복잡도가 반드시 성능 향상으로 이어지지 않음 (model 7의 경우)</li>
      <li>파이프라인 구축을 통해 실제 예측 시스템 구현이 가능함</li>
    </ul>
  </div>
  <div style="width: 48%; padding: 15px; border: 1px solid #ddd; border-radius: 8px; background-color: #f9f9f9;">
    <h3>🔍 활용 방안</h3>
    <ol>
      <li>헬스케어 앱에 행동 인식 기능 통합으로 사용자 활동 자동 기록</li>
      <li>음직임을 모니터링하여 동적인 움직임이 정적인 움직임보다 적을 경우, 움직일 수 있는 서비스를 웨어러블 기기나 스마트폰과 연동</li>
      <li>사용자 행동 패턴에 기반한 개인화된 서비스 제공</li>
      <li>스마트홈 시스템과 연동하여 사용자 행동에 따른 맞춤형 환경 제어</li>
      <li>노인 케어 시스템에 낙상 감지 기능 구현 가능</li>
    </ol>
  </div>
</div>

<br>

## 💡 프로젝트 배운 점

<div align="center">
  <table>
    <tr>
      <td width="30%" align="center">📊<br><b>특성 선택</b></td>
      <td width="70%">많은 특성(561개) 중 중요도 기반으로 핵심 특성을 선별하는 기법 습득</td>
    </tr>
    <tr>
      <td align="center">🔄<br><b>계층적 모델링</b></td>
      <td>복잡한 다중 분류 문제를 더 작은 단위로 분해하여 해결하는 접근법 학습</td>
    </tr>
    <tr>
      <td align="center">🤖<br><b>딥러닝 최적화</b></td>
      <td>드롭아웃, 조기 종료 등 과적합 방지 기법의 효과적인 적용 방법 습득</td>
    </tr>
    <tr>
      <td align="center">📈<br><b>신뢰구간 평가</b></td>
      <td>단순 정확도가 아닌 신뢰구간을 활용한 모델 평가의 중요성 인식 - 정확도 뿐만 아니라 모델 예측의 신뢰성도 고려해야 함</td>
    </tr>
    <tr>
      <td align="center">🔍<br><b>세분화된 분류</b></td>
      <td>단일 복잡 모델의 높은 정확도보다 문제를 세분화하여 각 하위 문제를 정확하게 해결하는 접근법이 더 효과적임을 학습</td>
    </tr>
    <tr>
      <td align="center">⚙️<br><b>파이프라인 구축</b></td>
      <td>복잡한 데이터 처리 및 다단계 예측 과정을 일관된 흐름으로 구현하는 기술 습득</td>
    </tr>
    <tr>
      <td align="center">💼<br><b>센서 데이터 이해</b></td>
      <td>가속도계, 자이로스코프 센서 데이터의 특성과 의미에 대한 이해 심화</td>
    </tr>
  </table>
</div>
<br>

## 🛠️ 기술 스택

<div align="center">
  <table>
    <tr>
      <th colspan="2" align="center">분류</th>
      <th align="center">기술</th>
      <th align="center">용도</th>
    </tr>
    <tr>
      <td rowspan="4" width="10%">💻</td>
      <td width="20%"><b>언어</b></td>
      <td width="25%">Python</td>
      <td width="45%">전체 프로젝트 개발</td>
    </tr>
    <tr>
      <td rowspan="2"><b>데이터 처리</b></td>
      <td>Pandas</td>
      <td>데이터프레임 조작 및 전처리</td>
    </tr>
    <tr>
      <td>NumPy</td>
      <td>수치 연산 및 배열 처리</td>
    </tr>
    <tr>
      <td><b>시각화</b></td>
      <td>Matplotlib, Seaborn</td>
      <td>데이터 시각화 및 결과 표현</td>
    </tr>
    <tr>
      <td rowspan="3">🤖</td>
      <td rowspan="2"><b>머신러닝</b></td>
      <td>Scikit-learn</td>
      <td>데이터 전처리, 모델 평가</td>
    </tr>
    <tr>
      <td>TensorFlow, Keras</td>
      <td>신경망 모델 구현 및 학습</td>
    </tr>
    <tr>
      <td><b>개발 환경</b></td>
      <td>Google Colab</td>
      <td>코드 개발 및 학습 환경</td>
    </tr>
  </table>
</div>

<br>

---

<div align="center">
  <p>본 프로젝트는 KT AIVLE School AI 트랙 미니프로젝트 3차로 진행되었습니다.</p>
  <p>© 2025 KT AIVLE School 6기 AI 트랙 미니프로젝트</p>
</div>
