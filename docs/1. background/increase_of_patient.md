# 우울증 환자의 증가

---

### 국내 우울증 환자 수

국내 우울증 환자의 [2020 ~ 2024년 우울증 환자 수 통계](https://theindigo.co.kr/archives/64060)에 따르면, <mark>2023년 국내 우울증 환자의 수가 100만명</mark>을 넘은 것으로 집계됩니다.

```vegalite
{
  "description": "2020 ~ 2024년 우울증 환자 수 통계를 막대 그래프로 시각화한 차트입니다.",
  "data": {"url" : "assets/charts/data/depression_patient_data.json"},
  "mark": {"type": "line", "tooltip": true, "point": true},
  "encoding": {
    "x": {"field": "년도", "type": "nominal", "axis": {"labelAngle": 0}},
    "y": {"field": "환자 수", "type": "quantitative", "scale": {"domain": [800000, 1200000]}}
  }
}
```

!!! warning "주의 사항"

    우울증 환자의 동일한 기준, 수치가 공개되어 있지 않아서, 국민건강보험공단 자료를 인용한 국회 의원의 자료를 참고하였습니다.

    해당 자료는 진료를 받은 환자 수(병원을 방문한 수)일 가능성이 높음, 실제 우울증을 경험했지만 치료를 받지 않은 사람까지 모두 포함한 유병률과는 다릅니다.

--- 유병률 내용 추가 예정 ---
