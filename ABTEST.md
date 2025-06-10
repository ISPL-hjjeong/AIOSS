# 🔬 ABTEST: Transformer 기반 In-loop Filter 성능 검증 실험

## 🎯 Objective
**VVC 압축 효율 및 성능 향상을 위한 Transformer 기반 in-loop filter 기술 개발 🚀**

본 실험은 기존 VVC의 anchor in-loop filter 대비 Transformer 기반 필터가 실제 압축 성능(BD-BR, BD-PSNR 등)을 향상시키는지 검증하기 위한 A/B Testing

---

## 🎯 Key Results (KR)

- **KR1:** Transformer 기반 in-loop filter 설계 및 BD-BR 기준 0.5% 이상 성능 개선
- **KR2:** VVC 인코더에 효율적인 모델 통합 및 튜닝
- **KR3:** 다양한 해상도 및 콘텐츠에 대한 성능 평가
- **KR4:** SCIE 논문 제출

---

## 🔍 기본 가설

> **If** the traditional in-loop filter (Deblocking Filter, SAO, ALF) is replaced with a Transformer-based neural in-loop filter,  
> **then** the coding performance will improve by reducing the BD-BR by **at least 0.5%** and increasing BD-PSNR by **more than 0.1 dB**,  
> across multiple video resolutions and content types.

---

## 🧠 가설 구성 요소별 상세 설명

### 🔹 1. 관찰 기반 문제점 (Observation)
기존 VVC의 in-loop filter는 복잡한 텍스처나 고주파 영역에서 압축 손실 복원이 부족하며,  
일반적인 공간 기반 필터링만을 수행하여 복원 품질에 한계가 있음.

---

### 🔹 2. 변경 요소 (Independent Variable)
- 기존 in-loop filter 체계 (DF + SAO + ALF)를 Transformer 기반 Neural Filter로 대체
- CTU 단위에서 Transformer가 spatial 및 frequency 정보를 동시에 처리

---

### 🔹 3. 기대 효과 (Expected Outcome)
- BD-BR이 평균 **0.5% 이상 감소** (압축 효율 개선)  
- BD-PSNR이 **0.1 dB 이상 증가** (복원 화질 개선)  
- 특히 **텍스처가 복잡한 장면**이나 **고해상도(4K)** 시퀀스에서 더 큰 성능 향상 예상

---

### 🔹 4. 측정 방식 (Dependent Variable)
- CTC 기준 클래스별 **1080p 및 4K 시퀀스**를 대상으로 실험  
- 동일 anchor 설정에서 **in-loop filter만 변경**하여 A/B 실험  
- 실험 결과를 **BD-BR (%)**, **BD-PSNR (dB)** 로 정량 평가

---

### 🔹 5. 평가 기준
- BD-BR ≥ 0.5% 감소 AND BD-PSNR ≥ 0.1 dB 증가 → **가설 채택**  
- 미달하거나 유의미하지 않을 경우 → **가설 보류 또는 수정 후 재실험**

---

## 📌 가설 요약
> Transformer 기반 Neural In-loop Filter는 기존 VVC 필터 대비 높은 표현력과 적응성을 통해 압축 손실 복원 성능을 개선할 수 있으며, 이에 따라 BD-BR 및 BD-PSNR에서 유의미한 성능 향상이 기대된다.
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
