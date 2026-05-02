# 🚀 Next Actions (session-state)

### 🕒 마지막 업데이트: 2026-05-02
이 문서는 글로벌 지침(~/.gemini/GEMINI.md)에 따라 다음 세션에서 즉시 수행해야 할 작업 목록을 관리합니다.

---

### 🎯 직전 세션 성과 요약
- 상속 기반 문서 아키텍처 정립 (`Kernel` -> `Domain` -> `Spec`)
- `/kb:*` 슬래시 커맨드 자동완성 인프라 구축
- `GEMINI.md`에 브레이크 프로토콜 및 정보 유실 방지 정책 반영

### 🚀 다음 세션 즉시 실행 항목 (Priority)
1. **정체성 복기**: `GEMINI.md`를 읽고 '환경 관리자'로서의 경계(OpenClaw와의 분리)를 재확인할 것.
2. **사후 진단**: 설치된 OpenClaw 데몬이 정상 작동하는지 `openclaw doctor`로 최종 점검.
3. **리소스 모니터링**: 메모리 사용량이 높은 상태이므로, OpenClaw 실행 시의 리소스 변화 추적.

### 💡 참고 사항
- 세션 시작 시 `GEMINI.md`와 본 문서를 가장 먼저 읽고 흐름을 이어가야 함.
- 모든 문서 작업은 `SKILL_IMPLEMENTATION_PROTOCOL.md` 규격을 준수할 것.
