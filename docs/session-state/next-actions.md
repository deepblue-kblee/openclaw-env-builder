# 🚀 Next Actions (session-state)

### 🕒 마지막 업데이트: 2026-05-02
이 문서는 글로벌 지침(~/.gemini/GEMINI.md)에 따라 다음 세션에서 즉시 수행해야 할 작업 목록을 관리합니다.

---

### 🎯 직전 세션 성과 요약
- **지침 통합**: `AGENTS.md`와 `CLAUDE.md`를 `GEMINI.md`로 통합하여 단일 진실 공급원(SSOT) 구축.
- **오류 해결**: Ollama `gemma4` 모델 404 오류를 모델 복사(cp)를 통해 해결하여 OpenClaw TUI 정상화.
- **자동화 인프라**: `/kb:wrap-up`, `/kb:briefing` 커맨드를 구현하여 세션 연속성 보장 체계 수립.

### 🚀 다음 세션 즉시 실행 항목 (Priority)
1. **정체성 복기**: `/kb:briefing`을 실행하여 새 세션 시작.
2. **사후 진단**: `openclaw doctor`를 실행하여 게이트웨이 및 플러그인 상태 최종 점검.
3. **리소스 최적화**: 메모리 사용량 저감을 위해 macOS 배경화면 단색 변경 등 최적화 작업 수행.

### 💡 참고 사항
- 세션 시작 시 `GEMINI.md`와 본 문서를 가장 먼저 읽고 흐름을 이어가야 함.
- 모든 문서 작업은 `SKILL_IMPLEMENTATION_PROTOCOL.md` 규격을 준수할 것.
