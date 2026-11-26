# wafer_test_W21.xlsx 요약

원본: `data/wafer_test_W21.xlsx` (616행 × 18열), lot LOT2611-07, wafer W21 (행 1개 = 다이 1개)

## 판정
- PASS 531개 (86.2%), FAIL 85개 (13.8%)

## 불량 유형
| 유형 | 개수 |
|---|---|
| none | 531 |
| leakage | 33 |
| vth_shift | 30 |
| open_short | 9 |
| parametric | 7 |
| particle | 6 |

## 영역(zone)별 불량률
| zone | PASS | FAIL | 불량률 |
|---|---|---|---|
| center | 79 | 1 | 1.2% |
| mid | 288 | 16 | 5.3% |
| edge | 164 | 68 | 29.3% |

## 불량유형 × 영역 (FAIL만)
| fail_type | center | mid | edge | 합계 |
|---|---|---|---|---|
| leakage | 0 | 0 | 33 | 33 |
| open_short | 0 | 7 | 2 | 9 |
| parametric | 0 | 4 | 3 | 7 |
| particle | 1 | 4 | 1 | 6 |
| vth_shift | 0 | 1 | 29 | 30 |
| 합계 | 1 | 16 | 68 | 85 |

## 판정별 평균 (단위: radius mm, vth V, idsat mA, ioff nA, rc Ω, ox nm — `templates/합격기준표.md` 기준)
| pass_fail | radius_mm | vth_v | idsat_ma | ioff_na | rc_ohm | ox_thk_nm | particle_cnt |
|---|---|---|---|---|---|---|---|
| FAIL | 120.25 | 0.5 | 1.04 | 15.93 | 9.65 | 2.97 | 1.04 |
| PASS | 89.04 | 0.46 | 1.05 | 2.19 | 7.89 | 2.98 | 0.59 |

## 기준표 검증
`templates/합격기준표.md`로 재판정한 결과, 엑셀의 `fail_type`과 다른 행은 **0개**입니다.

## 열 분류
- 수치형 연속: radius_mm, center_x_mm, center_y_mm, vth_v, idsat_ma, ioff_na, rc_ohm, ox_thk_nm
- 수치형 이산: die_x, die_y, particle_cnt
- 범주형: zone, bin, fail_type, pass_fail
- 이진형: crack
- 제외: lot_id, wafer_id(값 1개)
- bin, fail_type은 pass_fail과 같은 정보라 예측 시 입력에서 빼야 합니다.
