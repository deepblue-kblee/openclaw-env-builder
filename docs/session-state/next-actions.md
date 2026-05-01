# 🚀 Next Actions (session-state)

### 🕒 마지막 업데이트: 2026-05-02
이 문서는 글로벌 지침(~/.gemini/GEMINI.md)에 따라 다음 세션에서 즉시 수행해야 할 작업 목록을 관리합니다.

---

### 🎯 직전 세션 성과 요약
- 상속 기반 문서 아키텍처 정립 (`Kernel` -> `Domain` -> `Spec`)
- `/kb:*` 슬래시 커맨드 자동완성 인프라 구축
- `AGENTS.md`에 브레이크 프로토콜 및 정보 유실 방지 정책 반영

### 🚀 다음 세션 즉시 실행 항목 (Priority)
1. **환경 진단**: `/kb:sys-stat` 실행하여 `jarvis` 계정 상태 최종 확인.
2. **명세 동기화**: `/kb:oc-update setup` 실행하여 최신 설치 가이드 수집 및 분석.
3. **설치 프로세스 진입**: 결정된 방식(curl 또는 pnpm)에 따라 OpenClaw 설치 가이드 및 실행.

### 💡 참고 사항
- 세션 시작 시 `AGENTS.md`와 본 문서를 가장 먼저 읽고 흐름을 이어가야 함.
- 모든 문서 작업은 `SKILL_IMPLEMENTATION_PROTOCOL.md` 규격을 준수할 것.
