# Report Generator (Antigravity / Gemini Edition)

**데이터 파일을 넣고 한 문장으로 요청하면, 에이전트 팀 5명이 차례로 일해서 업무 보고서 한 벌을 만드는 Google Antigravity(Gemini) 하네스입니다.**

[English](README.md) · 한국어

```
데이터 정리 → 분석 → 시각화 → 집필 → 경영진 요약·검증 → HTML 보고서
```

## 무엇이 나오나요

| 파일 | 내용 |
|---|---|
| `report.html` | 더블클릭으로 여는 한 장짜리 보고서 (경영진 요약, KPI 카드, 차트, 본문, 액션 아이템). 인쇄 가능 |
| `01_data_collection.md` | 정리된 데이터와 출처 |
| `02_analysis_report.md` | 분석 결과와 계산 기록 |
| `03_visualization_spec.md` | 차트 명세, SVG 차트, Excel/PPT 재현 가이드 |
| `04_full_report.md` | 보고서 본문 |
| `05_executive_summary.md` | 경영진 1페이지 요약 + 검증 보고서 |

완성되면 **바탕화면과 다운로드의 `보고서_결과물` 폴더**에 자동으로 복사되고 폴더가 열립니다.

## 필요한 것

| 도구 | 필수 여부 | 용도 |
|---|---|---|
| Google Antigravity (데스크톱 앱) | 필수 | Gemini 에이전트 실행 |
| Python 3.10+ | 필수 | 계산 검산, 엑셀 읽기, 결과 폴더 열기. 없으면 에이전트가 설치합니다 |
| Git | 저장소를 받을 때 | 없으면 에이전트가 설치합니다 |

유료 API 키는 필요 없습니다.

## 시작하기

### 방법 A. 채팅창에 붙여넣기 (수업 권장)

안티그라비티 채팅창에 아래 문장을 그대로 붙여넣으세요.

```text
https://github.com/AI-in-2hour/report-generator 저장소를 내 컴퓨터에 받고, 그 폴더의 SKILL.md를 먼저 읽고 그 절차대로 진행해줘. samples/kingo-healthcare 데이터로 킹고 헬스케어 베트남 진출 전략 보고서를 경영진 보고용으로 빠르게 만들어줘.
```

중간에 `Allow ... ?` 창이 뜨면 **1번(이번만 허용)** 또는 **2·3번(항상 허용)** 을 고르고 Enter를 누르세요. **4번(No)은 누르지 마세요.**

### 방법 B. 폴더를 워크스페이스로 열기

```bash
git clone https://github.com/AI-in-2hour/report-generator.git
```

안티그라비티에서 `report-generator` 폴더를 열면 `GEMINI.md`가 자동으로 적용됩니다. 그다음 채팅창에 요청만 쓰면 됩니다.

## 요청 예시

```text
samples/kingo-healthcare 데이터로 킹고 헬스케어 베트남 진출 전략 보고서를 경영진 보고용으로 빠르게 만들어줘
```

```text
input 폴더에 넣은 매출 데이터로 3분기 실적 보고서 만들어줘. 보고 대상은 팀장이야
```

```text
이 보고서 경영진용으로 1페이지 요약해줘
```

요청에 **"빠르게"** 가 들어가면 웹 검색 없이 제공 데이터만 쓰고, 차트 3개 이하로 짧게 만듭니다.

## 내 데이터로 해 보기

1. `input/` 폴더에 CSV, 엑셀, PDF, 워드, 텍스트 파일을 넣습니다.
2. "input 폴더 데이터로 ○○ 보고서 만들어줘"라고 요청합니다.

> ⚠️ **회사 기밀, 고객 개인정보, 비밀번호는 넣지 마세요.** 회사 자료는 소속 회사의 AI 사용 정책을 먼저 확인하세요. 실습은 `samples/`의 가상 데이터로 하는 것을 권장합니다.

## 폴더 구조

```text
report-generator/
├── GEMINI.md              워크스페이스로 열면 자동 적용되는 안내
├── SKILL.md               전체 절차 (오케스트레이터)
├── agents/                역할 5개의 지침
├── references/            차트 선택 기준, KPI 분석 기준
├── samples/               실습용 가상 데이터 (킹고 헬스케어)
├── input/                 내 데이터를 넣는 곳
├── scripts/open_results.py 결과를 바탕화면·다운로드로 복사하고 폴더 열기
└── _workspace/            실행할 때마다 만들어지는 작업 폴더
```

## 라이선스와 출처

- [Apache License 2.0](LICENSE)으로 배포합니다.
- 원본: [revfactory/harness-100](https://github.com/revfactory/harness-100)의 `ko/82-report-generator` (Apache-2.0, Copyright 2026 Robin)
- Antigravity / Gemini용 수정: AI-IN ([AI-in-2hour](https://github.com/AI-in-2hour), 2026-11). 바꾼 점은 [NOTICE](NOTICE)에 있고, 수정한 파일마다 맨 위에 수정 안내가 있습니다.
- 이 저장소는 원작자와 제휴하거나 원작자가 보증한 것이 아닙니다.
