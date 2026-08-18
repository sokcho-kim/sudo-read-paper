# Recent use of deep learning techniques in clinical applications based on gait: a survey

| 항목 | 내용 |
|------|------|
| 저자 | Yume Matsushita, Dinh Tuan Tran, Hirotake Yamazoe, Joo-Ho Lee |
| 소속 | Ritsumeikan University |
| 출처 | [DOI: 10.1093/jcde/qwab054](https://doi.org/10.1093/jcde/qwab054) |
| 학회/연도 | Journal of Computational Design and Engineering, 2021, 8(6), 1499–1532 |
| 읽은 날짜 | 2026-08-18 |
| 상태 | summary |
| 분야 | Deep Learning / Gait / Clinical |

## 한 줄 요약

보행(gait) 기반 임상 응용에 딥러닝을 적용한 2018~2020년 연구를 응용 분야 × 센싱 모달리티 × DL 모델 × 공개 데이터셋의 대응 관계로 체계화한 서베이 — 최대 난제는 임상 보행 데이터의 절대량 부족이고, 해법으로 데이터 증강·약지도학습·전이학습을, 향후 초점으로 XAI와 IoT를 꼽는다.

## 핵심 기여

1. **"임상 보행 분석 + 딥러닝"을 종합 개관한 최초의 서베이** (저자 주장) — 임상 응용 분류(Fig. 2)와 센싱 모달리티 분류(Fig. 3), 두 개의 택소노미 제안
2. **응용별 적합 모달리티 가이드** — 원격 모니터링은 착용형 관성 센서, 통제 환경 임상 평가는 비전 기반, 외골격 제어는 착용형, 로봇 재활(RAGT)은 마커리스 비전 등 센서 선택 지침 제공
3. **데이터 부족 대응 기법 3종 정리** — 데이터 증강(기하 변환·SMOTE·GAN), 약지도학습(능동학습·준지도), 전이학습(도메인 적응·멀티태스크·사전학습 재사용)
4. **공개 보행 데이터셋 18개 정리** (Table 7) — 낙상 / 파킨슨병 / 기타 이상 보행 3분류

## 구조 미리보기 (읽을 때 지도)

- **§2~3 기초**: 보행 주기(stance 62% / swing 38%, 6구간 세분)와 임상 보행 파라미터 → 보행 이상을 신경학적·근골격계·복합 원인으로 분류 (cautious/senile/waddling/antalgic gait)
- **§4 임상 응용**: ① 원격 모니터링(낙상 위험·감지·예측, FoG 감지·예측) ② 의사 지원(진단, 중증도 평가 — UPDRS/UHDRS 정량화, 복약 상태) ③ 보행 위상 인식(이산 vs 연속 — 외골격·의족 제어용)
- **§5 모달리티**: 비착용형(비전 MB/ML, 바닥 센서, 레이더) vs 착용형(인솔, IMU, EMG/EEG) vs 하이브리드 — Table 3에 장단점 정리. 레이더는 고비용·간섭 문제로 리뷰에서 제외
- **§6 DL 적용**: CNN(센서 시계열의 이미지 변환 입력 포함), RNN(LSTM/GRU, Bi-, attention, ConvLSTM), AE(디노이징·이상 감지), GAN(데이터 증강), CNN+RNN 하이브리드 — 그리고 데이터 부족 대응 3종
- **§7 데이터셋**: 낙상(SmartFall, SisFall, MobiAct, UR Fall, tFall), PD(Daphnet FoG, mPower, PhysioNet Gait in PD — vGRF 대규모라 선호됨), 기타(GaitRec 75k trial, PhysioNet 신경퇴행성). 낙상·이상 보행 데이터 다수가 **건강인의 모의 데이터**라는 점 주의
- **§8 과제**: ① 데이터 부족 → 과적합 ② 블랙박스 — XAI 적용 사례 아직 소수(salient map으로 파킨슨 바이오마커 발견, LRP, LIME) ③ XAI 평가에 임상 전문가 협력 필수 ④ IoT 연산 한계·프라이버시 (분산 계층형 NN 등)

## 눈여겨볼 포인트

- 가장 많이 연구된 질환은 **파킨슨병**, 원격 모니터링의 최다 모달리티는 **착용형 IMU**
- FoG "예측"이 "감지"보다 훨씬 적은 이유: pre-FoG 구간 정의 자체가 모호 (보통 동결 1~6초 전 고정 윈도우)
- 시계열 센서를 이미지로 변환(스펙트로그램, recurrence plot, 족저압 이미지)해서 CNN에 넣는 패턴이 반복 등장
- 성능 예시: 1D-CNN으로 PD 검출 98.7% (El Maachi 2020), Bi-LSTM 미세 보행 변화 82% (Turner & Hayes 2019)
- X-VARS 리뷰와 연결점: 여기서도 결론이 **설명가능성(XAI)** — 임상 도메인에서 블랙박스가 수용의 병목이라는 문제의식이 동일

## 한줄평

새 지식보다는 지형도를 주는 논문 — 질환·센서·모델·데이터셋의 조합 공간을 한눈에 잡아주므로, 보행 관련 과제를 시작할 때 "어떤 센서로 어떤 모델부터"를 정하는 출발점으로 유용하다. 단 커버 기간이 2018~2020이라 트랜스포머 이후 흐름은 없다.
