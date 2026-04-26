# 🤖 에이전트 시스템 루트 가이드 (AGENTS.md)

이 문서는 이 프로젝트의 모든 AI 에이전트가 작업 시작 전 반드시 숙지해야 하는 최상위 지침이다.

---

### 1. 핵심 철학 (Core Philosophy)
- 우리는 **'하네스 엔지니어링(Harness Engineering)'**을 준수한다.
- 실수가 발생하면 프롬프트가 아닌 **구조적 시스템(Harness)**을 고친다.
- 모든 위험 작업은 OpenClaw 자체 **Docker Sandbox** 내에서 수행한다.
- 상세 원칙: `docs/methodology/HarnessEngineering.md`

### 2. 세션 연속성 및 부팅 시퀀스 (Boot Sequence)
새로운 세션이 시작되면 반드시 아래 순서대로 문서를 읽고 작업을 재개해야 한다.
1. **Read AGENTS.md**: 최상위 원칙 및 역할 확인.
2. **Read docs/state/CURRENT_STATE.md**: 직전 세션의 상태와 **Pending Action** 파악.
3. **Read docs/roadmap/AGENT_SYSTEM_ROADMAP.md**: 전체 진행도 내 현재 위치 확인.
4. **Action**: `CURRENT_STATE.md`에 기록된 작업부터 즉시 수행.

### 3. 체크포인트 규칙 (Checkpoint Rule)
- 의미 있는 단일 작업(스크립트 작성, 환경 검사 등)이 끝날 때마다 반드시 `docs/state/CURRENT_STATE.md`를 최신화한다.

### 4. 필수 참조 문서 (Updated Paths)
- **로드맵**: `docs/roadmap/AGENT_SYSTEM_ROADMAP.md`
- **보안 정책**: `docs/policy/SANDBOX_POLICY.md`
- **방법론**: `docs/methodology/HarnessEngineering.md`
- **빠른 참조 (FAQ)**: `docs/user-help/QUICK_REF.md`

---
*주의: 모든 실행은 `docs/policy/SANDBOX_POLICY.md`의 보안 구역(Zone) 규칙을 따른다.*
