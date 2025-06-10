# 🔬 ABTEST: Transformer 기반 In-loop Filter 성능 검증 실험

## 🎯 Objective
**VVC 압축 효율 및 성능 향상을 위한 Transformer 기반 in-loop filter 기술 개발 🚀**

본 실험은 기존 VVC의 anchor in-loop filter 대비 Transformer 기반 필터가 실제 압축 성능(BD-BR, BD-PSNR 등)을 향상시키는지 검증하기 위한 A/B Testing입니다.

---

## 🎯 Key Results (KR)

- **KR1:** Transformer 기반 in-loop filter 설계 및 BD-BR 기준 0.5% 이상 성능 개선
- **KR2:** VVC 인코더에 효율적인 모델 통합 및 튜닝
- **KR3:** 다양한 해상도 및 콘텐츠에 대한 성능 평가
- **KR4:** SCIE 논문 제출

---

## ❓ 가설 (Hypothesis)

> If we replace the traditional in-loop filter with a Transformer-based in-loop filter,  
> then the BD-BR will improve by at least 0.5% and BD-PSNR will increase across multiple resolutions.

- **누구를 위한 변화인가?**  
  VVC를 사용하는 고효율 영상 압축 연구자 및 산업 사용자들
- **무엇을 변경하는가?**  
  기존 in-loop filter를 Transformer 기반 neural filter로 대체
- **왜 필요한가?**  
  더 나은 복원 품질 및 비트 절약을 통해 압축 효율을 향상시키기 위해

---

## 🧪 실험 설계 (Experiment Design)

| 항목 | 내용 |
|------|------|
| **변경 사항** | Transformer 기반 in-loop filter 삽입 |
| **비교 대상** | 기존 VVC anchor filter (DF, SAO, ALF) |
| **측정 지표** | BD-BR (%), BD-PSNR (dB), Encoding Time |
| **대상 데이터셋** | CTC 클래스별 1080p 및 4K 시퀀스 |
| **기대 변화** | BD-BR ≥ 0.5% 향상, BD-PSNR ≥ 0.1dB 증가 |
| **실험 기간** | 2025년 5월 ~ 2025년 6월 |
| **비교 방식** | 동일 anchor 설정에서 in-loop filter만 변경 (A vs. B 조건 비교) |

---

## 📊 실험 결과 요약

| 시퀀스 | 해상도 | BD-BR 감소율 (%) | BD-PSNR 증가량 (dB) | Encoding Time 변화 |
|--------|--------|------------------|----------------------|--------------------|
| BasketballDrive | 1920×1080 | **0.72%** | 0.18 dB | +3.4% |
| Tango2           | 3840×2160 | **0.68%** | 0.15 dB | +2.8% |
| Cactus           | 1920×1080 | **0.81%** | 0.20 dB | +4.2% |
| DaylightRoad     | 3840×2160 | **0.59%** | 0.12 dB | +3.7% |
| **평균**         | -       | **0.70%** | **0.16 dB** | **+3.5%** |

---

## ✅ 결론 및 향후 계획

- Transformer 기반 in-loop filter는 기존 anchor 대비 평균 BD-BR 0.7% 개선을 달성하였으며, PSNR 또한 향상됨을 확인
- 실험 결과를 바탕으로 모델 경량화 및 tuning을 추가 적용하여 실시간 처리에도 적합하도록 개선 예정
- 현재 추가 실험 진행 중이며, 7월말까지 논문 초안 작성 후, 8월 중순까지 게재를 목표로 하고 있음 

---
