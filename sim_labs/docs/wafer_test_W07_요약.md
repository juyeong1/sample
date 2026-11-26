# wafer_test_W07.xlsx 요약

원본: `data/wafer_test_W07.xlsx` (616행 × 18열), lot LOT2611-07, wafer W07 (행 1개 = 다이 1개)

## 판정
- PASS 557개 (90.4%), FAIL 59개 (9.6%)

## 불량 유형
| 유형 | 개수 |
|---|---|
| none | 557 |
| crack | 25 |
| parametric | 9 |
| vth_shift | 7 |
| leakage | 6 |
| open_short | 6 |
| particle | 6 |

## 영역(zone)별 불량률
| zone | PASS | FAIL | 불량률 |
|---|---|---|---|
| center | 70 | 10 | 12.5% |
| mid | 274 | 30 | 9.9% |
| edge | 213 | 19 | 8.2% |

## 불량유형 × 영역 (FAIL만)
| fail_type | center | mid | edge | 합계 |
|---|---|---|---|---|
| crack | 9 | 16 | 0 | 25 |
| leakage | 0 | 0 | 6 | 6 |
| open_short | 0 | 4 | 2 | 6 |
| parametric | 0 | 8 | 1 | 9 |
| particle | 1 | 2 | 3 | 6 |
| vth_shift | 0 | 0 | 7 | 7 |
| 합계 | 10 | 30 | 19 | 59 |

## 판정별 평균 (단위: radius mm, vth V, idsat mA, ioff nA, rc Ω, ox nm — `templates/합격기준표.md` 기준)
| pass_fail | radius_mm | vth_v | idsat_ma | ioff_na | rc_ohm | ox_thk_nm | particle_cnt |
|---|---|---|---|---|---|---|---|
| FAIL | 89.23 | 0.47 | 1.04 | 5.85 | 9.32 | 2.97 | 1.17 |
| PASS | 93.78 | 0.46 | 1.05 | 2.24 | 8.02 | 2.98 | 0.57 |

## 기준표 검증
`templates/합격기준표.md`로 재판정한 결과, 엑셀의 `fail_type`과 다른 행은 **0개**입니다.

## 열 분류
- 수치형 연속: radius_mm, center_x_mm, center_y_mm, vth_v, idsat_ma, ioff_na, rc_ohm, ox_thk_nm
- 수치형 이산: die_x, die_y, particle_cnt
- 범주형: zone, bin, fail_type, pass_fail
- 이진형: crack
- 제외: lot_id, wafer_id(값 1개)
- bin, fail_type은 pass_fail과 같은 정보라 예측 시 입력에서 빼야 합니다.
