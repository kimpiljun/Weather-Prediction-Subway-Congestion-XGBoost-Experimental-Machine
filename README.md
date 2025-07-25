# 🚇 날씨로 예측하는 지하철 혼잡도: XGBoost 실험기

서울 지하철, 매일 붐비는 시간은 정해져 있을까? 혹은 날씨가 변하면 이용량도 달라질까? 이 프로젝트는 기상 데이터와 머신러닝(XGBoost)을 활용하여 혼잡도를 예측해본 실험이다. 복잡한 도시의 리듬을 데이터로 읽어내는 과정 속에서 발견한 패턴과 인사이트를 정리했다.

---

## 🔍 분석 배경

서울의 교통은 기온, 강수량, 체감 온도 같은 기상 변수에 따라 영향을 받을 수 있다. 특히 우천, 한파, 폭염 등은 대중교통 이용 패턴에 변화를 주기 마련이다. 이 분석은 "날씨가 지하철 혼잡도에 어떤 영향을 줄까?" 라는 질문에서 출발했다.

---

## 📂 사용 데이터

서울교통공사 혼잡도 데이터 (1시간 단위, 주요 노선 중심)

기상청 AWS/ASOS 관측 데이터 (서울 각 지역별 1시간 단위)

분석 기간: 2021~2022년

---

## 🧹 데이터 전처리

- -99로 기록된 이상값 대체: 랜덤포레스트 회귀로 예측하여 치환

- 기상데이터와 지하철 데이터를 시간/위치 기준으로 병합

- 펜데믹 시기 데이터 제거: 비정상적 혼잡도를 제거하기 위해

- 클러스터링 및 스피어만 상관분석으로 유의미한 변수 추출

---

## 🤖 모델링

XGBoost 회귀 모델 사용

범주형 변수는 타깃 인코딩 적용

하이퍼파라미터 튜닝으로 성능 개선 (Grid Search)

---

## 🎯 예측 목표

각 지하철역의 1시간 단위 혼잡도 수치 (정량 예측)

---

## 📈 주요 결과

### 

<p align="center">
  🔬 One_paper summary
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/c09a2587-d320-4123-aee9-6a22aadb5844" width="1000" alt="지하철 혼잡도 요약 이미지">
</p>

출퇴근 시간대 외에 날씨 변수에 따라 갑작스러운 혼잡 변화 존재

특정 역은 날씨 민감도가 높았으며, 이를 바탕으로 군집화 가능

---

## 💡 인사이트 및 활용 방안

기상 변화 예보 기반 교통 혼잡 예측 서비스 가능성

역별 혼잡 민감도를 고려한 탄력적 열차 배차 시스템 설계

도시 계획/교통 정책 수립 시 참고 지표로 활용 가능

---

## 📁 관련 파일

EDA.ipynb : 데이터 탐색 및 전처리 과정

Modeling.ipynb : XGBoost 모델 학습 및 예측

---

## ✍️ 정리하며

날씨라는 외부 요인이 교통 패턴에 주는 영향은 생각보다 크다. 이 분석을 통해, 데이터 기반의 도시 운영이 단순한 기술의 영역을 넘어 사람 중심의 도시 설계로 이어질 수 있다는 가능성을 엿볼 수 있었다.

---

📘 작성자: **김필준 (Piljun Kim)**
📧 [kimpj1997@naver.com](mailto:kimpj1997@naver.com)
🔗 [포트폴리오 보기](https://www.notion.so/XGBoost-238481d8bb10800eb8c3c53f52848eca)
