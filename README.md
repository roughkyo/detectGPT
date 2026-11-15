# AI 글 탐지 실험실

DetectGPT(2023), Fast-DetectGPT(2024), KatFishNet(2025)의 원리를 체험하는 한국어 수업용 페이지입니다.

## 실행

별도 빌드 과정 없이 정적 웹 서버에서 `index.html`을 제공합니다.

```bash
python -m http.server 8765
```

브라우저에서 `http://localhost:8765/`로 접속합니다.

## 주요 기능

- 다음 토큰의 확률과 top-k 샘플링 실험
- DetectGPT의 확률 지형, Fast-DetectGPT의 계산 방식 설명
- 판정선과 ROC·AUROC 시뮬레이션
- 브라우저에서 GPT-2·T5-small을 실행하는 영어 실험실
- 한국어 쉼표·띄어쓰기 측정, 확인 퀴즈와 용어 사전

모델 파일은 처음 실행할 때 약 210MB를 다운로드합니다. CDN 라이브러리와 웹폰트도 인터넷 연결이 필요합니다. 입력 글은 브라우저에서 계산하며 별도 분석 서버로 전송하지 않습니다.

## 해석 시 주의

영어 모델 GPT-2와 작은 섭동 모델 T5-small을 사용하는 교육용 구현입니다. 논문과 모델·섭동 개수 등 실행 조건이 다르므로 논문의 성능을 재현한 결과로 해석할 수 없습니다. 한국어 실험실은 형태소 분석기와 학습된 분류기 없이 지표만 측정하며 AI 여부를 판정하지 않습니다. 가상 수치는 화면에 별도로 표시합니다. 탐지 점수 하나로 학생의 부정행위를 단정해서는 안 됩니다.

## 참고 논문

- Mitchell et al., DetectGPT, ICML 2023
- Bao et al., Fast-DetectGPT, ICLR 2024
- Park et al., KatFishNet, ACL 2025

## 사용 라이브러리·모델

- @xenova/transformers 2.17.2
- Xenova/gpt2, Xenova/t5-small
- Google Fonts: Noto Sans KR, JetBrains Mono

## 2026-11-16 문구 검토

humanize-kr의 정밀 절차로 본문을 진단·윤문·원문 대조했습니다. techdoc 문체(~함/~임)를 유지하고 어려운 표현과 긴 문장을 다듬었습니다. 111개 블록, 수치 표기, 계산 코드와 디자인 코드를 보존했습니다. 이 검토에서 논문 원본의 모든 주장·수치를 다시 검증한 것은 아닙니다.
