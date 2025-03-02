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
  <p><img src="https://github.com/username/har-project/raw/main/images/multiclass_kde.png" width="600px" alt="특징 분포 시각화" /></p>
  <small><i>센서 데이터 특성값의 행동별 분포</i></small>
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

<div align="center">
  <img src="https://github.com/username/har-project/raw/main/images/feature_importance.png" width="700px" alt="변수 중요도 분석" />
  <br>
  <small><i>변수 중요도 분석 결과 - 상위 핵심 변수들</i></small>
</div>

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
          <li><b>중요도 상위 변수들은 6개 행동을 세부적으로 구분하는데 효과적이지만, 정작 정적/동적 행동의 구분에는 덜 효과적</b></li>
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
          <li><b>흥미롭게도, 전체 모델에서 중요도가 낮은 하위 변수들이 정적/동적 행동 구분에는 더 효과적으로 작용</b></li>
        </ul>
      </td>
    </tr>
  </table>
</div>

<div align="center">
  <h4>변수 중요도에 따른 KDE 분포 비교</h4>
  <div style="display: flex; justify-content: space-between; margin-top: 20px;">
    <div style="width: 48%;">
      <img src="https://github.com/username/har-project/raw/main/images/top_feature_kde.png" width="100%" alt="중요도 상위 변수 KDE 플롯" />
      <p align="center"><small><i>중요도 상위 변수(tGravityAcc-energy()-X)의 KDE 분포<br/>LAYING은 분리되지만 다른 행동들은 구분이 어려움</i></small></p>
    </div>
    <div style="width: 48%;">
      <img src="https://github.com/username/har-project/raw/main/images/bottom_feature_kde.png" width="100%" alt="중요도 하위 변수 KDE 플롯" />
      <p align="center"><small><i>중요도 하위 변수(fBodyBodyGyroJerkMag-iqr())의 KDE 분포<br/>정적 행동(STANDING, SITTING)과 동적 행동(WALKING 계열)이 뚜렷하게 구분됨</i></small></p>
    </div>
  </div>
</div>

<div style="padding: 15px; border: 1px solid #ddd; border-radius: 8px; background-color: #f0f8ff; margin: 20px 0;">
  <p><b>🔍 주목할 점:</b> 위 KDE 플롯 시각화에서 볼 수 있듯이, 중요도가 높은 변수(좌측)는 LAYING 행동만 분리하고 나머지 행동들의 분포가 상당 부분 겹치는 반면, 중요도가 낮은 변수(우측)는 오히려 정적 행동과 동적 행동을 명확하게 구분합니다. 이는 모델 구축 시 단순히 전체 중요도가 높은 변수만 고려하는 것이 아니라, 문제의 계층적 특성에 맞는 변수 선택이 중요함을 보여줍니다.</p>
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

<div align="center">
  <img src="https://github.com/username/har-project/raw/main/images/models_comparison.png" width="700px" alt="모델 성능 비교 차트" />
  <br>
  <small><i>모델 구조별 정확도 비교 - 단순한 구조의 model7이 가장 높은 성능</i></small>
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

<div style="display: flex; justify-content: space-around; margin-top: 20px;">
  <div style="width: 32%;">
    <img src="https://github.com/username/har-project/raw/main/images/stage1_loss.png" width="100%" alt="1단계 모델 학습 곡선" />
    <p align="center"><small><i>1단계 모델 학습 곡선</i></small></p>
  </div>
  <div style="width: 32%;">
    <img src="https://github.com/username/har-project/raw/main/images/dynamic_loss.png" width="100%" alt="동적 행동 모델 학습 곡선" />
    <p align="center"><small><i>동적 행동 모델 학습 곡선</i></small></p>
  </div>
  <div style="width: 32%;">
    <img src="https://github.com/username/har-project/raw/main/images/static_loss.png" width="100%" alt="정적 행동 모델 학습 곡선" />
    <p align="center"><small><i>정적 행동 모델 학습 곡선</i></small></p>
  </div>
</div>

<br>

## 🌟 계층적 모델링 접근법

우리 프로젝트의 핵심은 복잡한 다중 분류 문제를 더 단순한 하위 문제로 분해하는 계층적 접근법입니다:

<div align="center">
  <img src="https://github.com/username/har-project/raw/main/images/hierarchical_approach.png" alt="계층적 모델링 접근법" width="700px">
  <br>
  <small><i>두 단계로 나누어 분류하는 계층적 모델 접근법</i></small>
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

<div align="center">
  <img src="https://github.com/username/har-project/raw/main/images/pipeline_results.png" alt="파이프라인 예측 결과" width="700px">
  <br>
  <small><i>파이프라인 모델의 테스트 데이터 예측 결과 - 0.97의 정확도 달성</i></small>
</div>

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

<div align="center">
  <p><b>📊 주요 관찰: 변수 중요도의 역설</b></p>
  <div style="width: 80%; padding: 15px; border: 1px solid #ddd; border-radius: 8px; background-color: #f0f8ff; margin: 0 auto; text-align: left;">
    <p>흥미로운 관찰 결과 중 하나는 <b>변수 중요도와 분류 효과성 간의 역설적 관계</b>입니다. 전체 6개 행동 분류에서 중요도가 높게 나온 변수들은 정작 가장 기본적인 구분인 정적/동적 행동 분류에는 효과적이지 않았습니다. 반면, 중요도가 낮게 평가된 하위 변수들이 정적/동적 행동을 명확하게 구분하는 데 더 효과적이었습니다.</p>
    <p>이는 <b>문제의 계층적 특성을 이해하고 각 단계에 맞는 특성을 선별</b>하는 것의 중요성을 보여줍니다. 이러한 통찰이 계층적 모델링 접근법의 효과성을 뒷받침합니다.</p>
  </div>
</div>

## 💡 결론 및 시사점

<div style="display: flex; justify-content: space-between;">
  <div style="width: 48%; padding: 15px; border: 1px solid #ddd; border-radius: 8px; background-color: #f9f9f9;">
    <h3>📝 연구 결론</h3>
    <ul>
      <li><b>계층적 접근법의 우수성:</b> 복잡한 다중 분류 문제를 단계별로 해결하는 방식이 단일 모델보다 효과적</li>
      <li><b>이진 분류의 높은 정확도:</b> 정적/동적 행동 구분은 99.9%의 정확도로 매우 신뢰성 높게 수행 가능</li>
      <li><b>행동 유형별 정확도 차이:</b> 동적 행동(99%)이 정적 행동(96%)보다 세부 분류가 더 정확함 - 정적 행동 간 유사성이 더 높기 때문</li>
      <li><b>모델 단순화의 효과:</b> 더 복잡한 구조가 아닌, 최적화된 간결한 모델(model 7)이 더 좋은 성능 달성</li>
      <li><b>파이프라인 자동화:</b> 데이터 전처리부터 예측까지 일관된 파이프라인 구축으로 실시간 예측 시스템 구현 가능</li>
    </ul>
  </div>
  <div style="width: 48%; padding: 15px; border: 1px solid #ddd; border-radius: 8px; background-color: #f9f9f9;">
    <h3>🔍 실용적 활용 방안</h3>
    <ul>
      <li><b>건강 관리 시스템:</b> 일일 활동량 자동 기록, 칼로리 소모 추적, 운동 패턴 분석을 통한 맞춤형 피트니스 코칭</li>
      <li><b>활동 촉진 서비스:</b> 장시간 정적 행동 시 알림 제공, 규칙적인 움직임 유도로 건강한 생활 습관 형성 지원</li>
      <li><b>맞춤형 UX:</b> 사용자의 현재 행동 상태에 따라 스마트폰 인터페이스와 알림 방식을 자동 최적화</li>
      <li><b>스마트홈 연동:</b> 행동 패턴 감지에 따른 자동 조명 조절, 실내 온도 제어, 음악/미디어 추천 등 환경 최적화</li>
      <li><b>안전 모니터링:</b> 노인이나 장애인의 비정상적 행동 패턴 감지, 낙상 즉시 알림, 응급 상황 자동 대응 시스템</li>
      <li><b>교통 및 도시 계획:</b> 대규모 인구의 행동 패턴 분석을 통한 대중교통 최적화 및 도시 인프라 계획 지원</li>
    </ul>
  </div>
</div>

<br>

## 🧠 프로젝트 배운 점

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

## 🔜 향후 계획

- 추가 센서 데이터(자기장계, 기압계 등) 활용 모델 확장
- 실시간 행동 인식을 위한 경량화 모델 개발
- 사용자 개인화를 위한 온라인 학습 기능 구현
- 더 세분화된 행동 분류(달리기, 자전거 타기 등) 확장
- 실제 모바일 앱에 통합하여 서비스 구현

<br>

---

<div align="center">
  <p>본 프로젝트는 KT AIVLE School AI 트랙 미니프로젝트 3차로 진행되었습니다.</p>
  <p>© 2025 KT AIVLE School 6기 AI 트랙 미니프로젝트</p>
</div>
