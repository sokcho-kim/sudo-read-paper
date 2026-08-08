# sudo-read-paper

Couldn't read papers as a normal user, so I tried sudo.

## Index

| # | 날짜 | 논문 | 분야 | 노트 | 발표 |
|---|------|------|------|------|------|
| 1 | 2026-08-08 | [X-VARS: Introducing Explainability in Football Refereeing with Multi-Modal Large Language Models](https://arxiv.org/abs/2404.06332) | Multimodal LLM / Sports | [note](papers/2026-08-08-x-vars/note.md) · [review](papers/2026-08-08-x-vars/review.md) | [slides](papers/2026-08-08-x-vars/slides.md) |

## 구조

- `papers/YYYY-MM-DD-슬러그/` — 논문 하나당 폴더 하나 (`note.md` + 발표 시 `slides.md`, `assets/`)
- `templates/` — 요약(`summary.md`) · 정독(`review.md`) · 발표(`slides.md`, Marp) 템플릿
- 논문 PDF 원본은 커밋하지 않음 (노트에 원문 링크 기록)

노트는 `summary → deep → presented`로 자란다. 발표자료는 Marp 마크다운으로 작성하고 필요할 때 변환한다:

```bash
npx @marp-team/marp-cli papers/<폴더>/slides.md -o slides.pptx
```
