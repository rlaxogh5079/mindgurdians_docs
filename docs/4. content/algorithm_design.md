# 알고리즘 설계

---

<table border="1" cellspacing="0" cellpadding="6">
  <tr>
    <th>설계</th>
    <th>설계 요소</th>
    <th>설명</th>
  </tr>

  <tr>
    <td rowspan="3">알고리즘</td>
    <td><a href="https://www.frontiersin.org/journals/psychiatry/articles/10.3389/fpsyt.2024.1371946/full" target="_blank">스트레스/불안 알고리즘</a></td>
    <td>
      ① 스마트밴드 기반 생체 데이터 [HRV] 10Hz로 수집<br>
      ② 시계열 분할(윈도잉) 및 전처리(필터링)<br>
      ③ 심장 박동 피크 탐지(HeartPy 알고리즘) 후 IBI 산출<br>
      ④ HRV 특성치 계산(실시간/분 단위)<br>
      └ 시간: RMSSD, SDNN, SDSD, pNN50<br>
      └ 주파수: LF(0.04–0.15 Hz), HF(0.15–0.40 Hz)<br>
      ⑤ 통계 연관성 분석 후 결과 도출
    </td>
  </tr>

  <tr>
    <td><a href="https://pubmed.ncbi.nlm.nih.gov/36616929/" target="_blank">수면 패턴 알고리즘</a></td>
    <td>
      ① 총 수면 시간, 수면 중 HRV, EMA 설문 수집<br>
      ② 데이터 전처리<br>
      └ 결측 데이터 제거<br>
      └ 개인 표준화<br>
      └ 예측 벡터 구성<br>
　　　&nbsp;&nbsp;(1) EMA → TST/HRV<br>
　　　&nbsp;&nbsp;(2) TST/HRV → EMA<br>
      ③ VAR 모델링 후 유의한 쌍 Granger 인과성 검정<br>
      ④ Granger 인과성 검정 통과 쌍 대상 IRF 계산
    </td>
  </tr>

  <tr>
    <td><a href="https://www.mdpi.com/1424-8220/20/3/718" target="_blank">감정 알고리즘(행복/슬픔/중립)</a></td>
    <td>
      ① 스마트밴드 기반 생체 데이터 [HRV] 실시간 수집<br>
      ② 시계열 분할(윈도잉) 및 전처리<br>
      └ HR에서 중립/타깃으로 나누어 시계열 확보<br>
      ③ 정규화를 통한 개인화 제거<br>
      └ 원시 HR(뒤 구간) − 앞 구간 평균 HR = 정규화 HR<br>
      ④ 원시·정규화 HR 특징 추출<br>
      └ 원시: 1–2차 차분 평균, 범위 등<br>
      └ 정규화: 상·하강, 진폭, 기울기 통계 등<br>
      ⑤ SelectKBest 상위 k개 특징 선택<br>
      ⑥ 모델 학습(GBDT/AdaBoost) 후 분류 결과 도출
    </td>
  </tr>

</table>

!!! warning

    수면 패턴 알고리즘의 경우, 논문을 찾을 수 없어서 비슷한 내용의 논문을 첨부하였지만, 해당 논문의 내용에 맞게 내용이 변경될 필요가 있습니다.
