# 유방암의 임파선 전이 예측 AI 경진대회

## 개요
림프절(임파선)은 암의 전이에 매우 치명적인 역할을 하기 때문에 림프절 전이 여부와 전이 단계를 파악하는 것이 암을 치료하고 진단하는 것에 있어서 매우 중요
<br>

## 주제
유방암 병리 슬라이드 영상과 임상 항목을 조합하여 유방암의 임파선 전이 여부 이진 분류
<br>

## 데이터
항목	코딩	설명
ID		부여번호
나이		진단시 나이
수술연월일	연-월-일	
진단명	"1: ductal
2: lobular
3. mucinous 
4. other"	histologic type
암의 위치	"1: Right
2: Left
3: Both"	
암의 개수	"1: single
2: multiple"	
암의 장경		암 Size (mm), 여러 개의 암일 경우 가장 큰 종양의 장경
NG	"1: NG1
2: NG2
3: NG3"	1은 핵의 모양이 정상에 가까운 경우, 2는 중간, 3은 정상으로부터 매우 달라진경우입니다. 
HG	"1: HG1
2: HG2
3: HG3
4. not graded"	"Grade 1 (scores of 3, 4, or 5): 조직학적 분화도가 좋아서 전체적으로 합산 점수가 낮은 경우 
Grade 2 (scores of 6 or 7)
Grade 3 (scores of 8 or 9) : 조직학적 분화도가 나빠서 합산점수가 큰 경우  
4: Only microinvasion present (not graded)"
HG_score_1	"1: score 1
2: score 2
3: score 3
4: not graded"	"(Tubule formation)
Score 1 (>75% of tumor area forming glandular/tubular structures)
Score 2 (10% to 75% of tumor area forming glandular/tubular structures)
Score 3 (<10% of tumor area forming glandular/tubular structures)
4: Only microinvasion present (not graded)"
HG_score_2	"1: score 1
2: score 2
3: score 3
4: not graded"	"(Nuclear Pleomorphism)
Score 1 (nuclei small with little increase in size in comparison with normal breast epithelial cells, regular outlines, uniform nuclear chromatin, little variation in size)
Score 2 (cells larger than normal with open vesicular nuclei, visible nucleoli, and moderate variability in both size and shape)
Score 3 (vesicular nuclei, often with prominent nucleoli, exhibiting marked variation in size and shape, occasionally with very large and bizarre forms)
4: Only microinvasion present (not graded)"
HG_score_3	"1: score 1
2: score 2
3: score 3
4: not graded"	"(Mitotic Rate)
Score 1 (≤3 mitoses per mm2)
Score 2 (4-7 mitoses per mm2)
Score 3 (≥8 mitoses per mm2)
4: Only microinvasion present (not graded)"
DCIS_or_LCIS_여부	"0: no DCIS/LCIS
1: DCIS/LCIS present, EIC(-)
2: DCIS/LCIS present, EIC(+)"	제자리암종 (DCIS)의 유무 
DCIS_or_LCIS_type	"1: non-comedo
2: comedo"	제자리 암종내 괴사 유무 
T_category	"0: Tis
1: T1
2: T2
3: T3
4: T4"	"pTis (DCIS): Ductal carcinoma in situ
pT1: Tumor ≤20 mm in greatest dimension
    pT1mi: Tumor ≤1 mm in greatest dimension
    pT1a: Tumor >1 mm but ≤5 mm in greatest dimension (round any measurement >1.0−1.9 mm to 2 mm)
    pT1b: Tumor >5 mm but ≤10 mm in greatest dimension
    pT1c: Tumor >10 mm but ≤20 mm in greatest dimension
pT2: Tumor >20 mm but ≤50 mm in greatest dimension
pT3: Tumor >50 mm in greatest dimension
pT4: Tumor of any size with direct extension to the chest wall and/or to the skin (ulceration or skin nodules) ###
    pT4a: Extension to the chest wall; invasion or adherence to pectoralis muscle in the absence of invasion of chest wall structures does not qualify as T4
    pT4b: Ulceration and/or ipsilateral macroscopic satellite nodules and/or edema (including peau d’orange) of the skin that does not meet the criteria for inflammatory ca
    pT4c: Both T4a and T4b are present
    pT4d: Inflammatory carcinoma"
ER	"0: -
1: +"	"Negative: <1% immunoreactive tumor cells present
Positive: Immunoreactive tumor cells present (≥1%)  여성호르몬중 에스트로겐 수용체의 발현 여부입니다. "
ER_Allred_score		정수로 기입 (0 ~ 8) : AS = PS + IS 
PR	"0: -
1: +"	"Negative: <1% immunoreactive tumor cells present
Positive: Immunoreactive tumor cells present (≥1%)  여성호르몬중 프로게스테론 수용체의 발현 여부입니다. "
PR_Allred_score		정수로 기입 (0 ~ 8) : AS = PS + IS 
KI-67_LI_percent		정수로 0~100 범위로 기입. 세포증식의 수치를 표시한 항목입니다. 
HER2	"0: -
1: +"	참고: IHC 와 SISH 까지 모두 고려한 결과로 기록, 세포성장이자 수용체의 발현여부를 표시 
HER2_IHC	"0: Negative (0)
1: Negative (1+)
2: Equivocal (2+)
3: Positive (3+)"	
HER2_SISH	"0: not amplified (negative)
1: amplified (positive)"	"[Dual Probe ISH Group Definitions]
- Group 1 = HER2/CEP17 ratio ≥2.0; ≥4.0 HER2 signals/cell
- Group 2 = HER2/CEP17 ratio ≥2.0; <4.0 HER2 signals/cell
- Group 3 = HER2/CEP17 ratio <2.0; ≥6.0 HER2 signals/cell
- Group 4 = HER2/CEP17 ratio <2.0; ≥4.0 and <6.0 HER2 signals/cell
- Group 5 = HER2/CEP17 ratio <2.0; <4.0 HER2 signals/cell

[Results]
- Amplified (Positive) (in IHC 2+): Group 3 and Group 1
- Not amplified (Negative) (in IHC 2+): Group 2, Group 4 and Group 5"
HER2_SISH_ratio		소수점 첫째자리까지 숫자로 기입
BRCA_mutation	"0: No BRCA1, BRCA2 mutation 
1: BRCA1 mutation 
2: BRCA2 mutation "	검사 시행 안한 경우 빈칸으로, 시행했으나 mutation (의미있는mutation만) 없는경우는 0, 유방암 관련 유전자변이 여부
N_category	"0: 임파선(림프절) 전이 X
1: 임파선(림프절) 전이 O"	![image](https://user-images.githubusercontent.com/107402707/219846965-05a283c3-b73a-44f5-b865-962f503388f7.png)


<br>


## 모델 구조
<br>

## 결과
<br>


#### 출처
[DACON 유방암의 임파선 전이 예측 AI 경진대회](https://dacon.io/competitions/official/236011/overview/description)
