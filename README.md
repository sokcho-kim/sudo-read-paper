# sudo-read-paper

Couldn't read papers as a normal user, so I tried sudo.

## Index

| # | 날짜 | 논문 | 분야 | 노트 | 발표 |
|---|------|------|------|------|------|
| 1 | 2026-08-08 | [X-VARS: Introducing Explainability in Football Refereeing with Multi-Modal Large Language Models](https://arxiv.org/abs/2404.06332) | Multimodal LLM / Sports | [note](papers/2026-08-08-x-vars/note.md) · [review](papers/2026-08-08-x-vars/review.md) | [slides](papers/2026-08-08-x-vars/slides.md) |
| 2 | 2026-08-18 | [Recent use of deep learning techniques in clinical applications based on gait: a survey](https://doi.org/10.1093/jcde/qwab054) | Deep Learning / Gait / Clinical | [note](papers/2026-08-18-gait-dl-survey/note.md) | - |
| 3 | 2026-08-25 | [Machine Learning Models for Reliable Gait Phase Detection Using Lower-Limb Wearable Sensor Data](https://doi.org/10.3390/app16031397) | Machine Learning / Gait Phase / Wearable | [note](papers/2026-08-25-gait-phase-detection/note.md) · [assets](papers/2026-08-25-gait-phase-detection/assets/) | - |

## 구조

- `papers/YYYY-MM-DD-슬러그/` — 논문 하나당 폴더 하나 (`note.md` + 발표 시 `slides.md`, `assets/`)
- `templates/` — 요약(`summary.md`) · 정독(`review.md`) · 발표(`slides.md`, Marp) 템플릿
- 논문 PDF 원본은 커밋하지 않음 (노트에 원문 링크 기록)

노트는 `summary → deep → presented`로 자란다. 발표자료는 Marp 마크다운으로 작성하고 필요할 때 변환한다:

```bash
npx @marp-team/marp-cli papers/<폴더>/slides.md -o slides.pptx
```
