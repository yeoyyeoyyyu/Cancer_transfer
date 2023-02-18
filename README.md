# 유방암의 임파선 전이 예측 AI 경진대회

## 개요
림프절(임파선)은 암의 전이에 매우 치명적인 역할을 하기 때문에 림프절 전이 여부와 전이 단계를 파악하는 것이 암을 치료하고 진단하는 것에 있어서 매우 중요
<br>

## 주제
유방암 병리 슬라이드 영상과 임상 항목을 조합하여 유방암의 임파선 전이 여부 이진 분류
<br>

## 데이터
|항목|label|설명|
|------|---|---|
|ID| |환자번호|
|나이| |진단시 나이|
|수술연월일|연-월-일||
|진단명|1: ductal<br>2: lobular<br>3. mucinous<br>4. other|histologic type<br>(조직학적 유형|
|암의 위치|1: Right<br>2: Left<br>3: Both||
|암의 개수|1: single<br>2: multiple||
|암의 장경||암 Size (mm), 여러 개의 암일 경우 가장 큰 종양의 장경|
|NG|1: NG1<br>2: NG2<br>3: NG3|1은 핵의 모양이 정상에 가까운 경우, 2는 중간, 3은 정상으로부터 매우 달라진경우입니다. |
|HG|1: HG1<br>2: HG2<br>3: HG3<br>4. not graded|Grade 1 (scores of 3, 4, or 5): 조직학적 분화도가 좋아서 전체적으로 합산 점수가 낮은 경우 <br>Grade 2 (scores of 6 or 7)<br>Grade 3 (scores of 8 or 9) : 조직학적 분화도가 나빠서 합산점수가 큰 경우  <br>4: Only microinvasion present (not graded)|
|HG_score_1|1: score 1<br>2: score 2<br>3: score 3<br>4: not graded|(Tubule formation)<br>Score 1 (>75% of tumor area forming glandular/tubular structures)<br>Score 2 (10% to 75% of tumor area forming glandular/tubular structures)<br>Score 3 (<10% of tumor area forming glandular/tubular structures)<br>4: Only microinvasion present (not graded)|
|HG_score_2|1: score 1<br>2: score 2<br>3: score 3<br>4: not graded|(Nuclear Pleomorphism)<br>Score 1 (nuclei small with little increase in size in comparison with normal breast epithelial cells, regular outlines, uniform nuclear chromatin, little variation in size)<br>Score 2 (cells larger than normal with open vesicular nuclei, visible nucleoli, and moderate variability in both size and shape)<br>Score 3 (vesicular nuclei, often with prominent nucleoli, exhibiting marked variation in size and shape, occasionally with very large and bizarre forms)<br>4: Only microinvasion present (not graded)|
|HG_score_3|1: score 1<br>2: score 2<br>3: score 3<br><br>4: not graded|(Mitotic Rate)<br>Score 1 (≤3 mitoses per mm2)<br>Score 2 (4-7 mitoses per mm2)<br>Score 3 (≥8 mitoses per mm2)<br>4: Only microinvasion present (not graded)|
|DCIS_or_LCIS_여부|0: no DCIS/LCIS<br>1: DCIS/LCIS present, EIC(-)<br>2: DCIS/LCIS present, EIC(+)|제자리암종 (DCIS)의 유무 |
|DCIS_or_LCIS_type|1: non-comedo<br>2: comedo|제자리 암종내 괴사 유무 |
|T_category|0: Tis<br>1: T1<br>2: T2<br>3: T3<br>4: T4|
<br>


## 모델 구조
<br>

## 결과
<br>


#### 출처
[DACON 유방암의 임파선 전이 예측 AI 경진대회](https://dacon.io/competitions/official/236011/overview/description)
