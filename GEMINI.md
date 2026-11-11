<!-- 수정 안내: 이 파일은 revfactory/harness-100 (Apache-2.0)의 ko/82-report-generator/.claude/CLAUDE.md 를 바탕으로 AI-IN이 2026-11 Google Antigravity(Gemini)용으로 새로 쓴 워크스페이스 안내 파일입니다. -->

# Report Generator — Antigravity (Gemini) 업무 보고서 하네스

이 워크스페이스는 데이터 파일을 넣고 한 문장으로 요청하면, 에이전트 팀 5명(데이터 정리 → 분석 → 시각화 → 집필 → 경영진 요약·검증)이 차례로 일해서 **업무 보고서 한 벌**을 만드는 하네스입니다.

## 에이전트 필수 행동 지침

1. 사용자가 보고서, 분석 보고서, 실적 보고, 경영진 요약, "이 데이터로 보고서" 같은 요청을 하면 **반드시 현재 폴더의 [`SKILL.md`](./SKILL.md)를 먼저 읽고** 그 절차(Phase 0 ~ Phase 4)를 그대로 따르세요.
2. 역할별 지침은 [`agents/`](./agents/) 폴더에, 차트·지표 기준은 [`references/`](./references/) 폴더에 있습니다. 각 역할을 시작하기 전에 해당 파일을 `read_file`로 읽으세요.
3. **사용자에게 명령어를 치라고 안내하지 마세요.** 계산 검산이나 결과 폴더 열기에 Python이 필요한데 설치되어 있지 않으면, 에이전트가 직접 `run_command`(`BypassSandbox: true`)로 설치합니다.
   - Windows: `winget install --accept-package-agreements --accept-source-agreements Python.Python.3.12`
   - macOS: `brew install python`
4. **사용자 데이터에 없는 수치를 지어내지 마세요.** 웹에서 가져온 수치는 출처 주소를 달고, 출처가 없는 값은 "추정"이라고 표시합니다.
5. 완성되면 `python scripts/open_results.py <작업 폴더>`로 결과를 **`바탕화면/보고서_결과물`과 `다운로드/보고서_결과물`에 복사하고 폴더를 열어 주세요.** 샌드박스 때문에 복사가 막히면 `BypassSandbox: true`로 다시 실행하고, 최종 답변 맨 위에 결과 파일 경로를 적어 주세요.
