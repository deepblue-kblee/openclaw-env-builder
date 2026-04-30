# 🤖 에이전트 시스템 루트 가이드 (AGENTS.md)

이 문서는 이 프로젝트의 모든 AI 에이전트가 작업 시작 전 반드시 숙지해야 하는 최상위 지침이다.

---

### 1. 핵심 철학 (Core Philosophy)
- 우리는 **'하네스 엔지니어링(Harness Engineering)'**을 이 프로젝트의 **운영 지침과 가이드라인**에만 적용한다.
- **OpenClaw**는 우리의 관리 대상이며, 에이전트는 독립된 macOS 계정 환경에서 OpenClaw가 최적의 성능을 낼 수 있도록 돕는 **'환경 헬퍼(Env Helper)'** 역할을 한다.
- **순차 완료 원칙 (Sequential Completion)**: 여러 작업이 주어졌을 때, 동시에 진행하지 않고 반드시 하나를 완벽히 해결(실행-리뷰-검증-평가-완료)한 후 다음 작업으로 넘어간다.
- **보안과 격리**: 샌드박스 대신 macOS의 사용자 계정 격리 기능을 활용하며, 메인 계정 데이터 보호를 최우선으로 한다.

### 2. 세션 연속성 및 부팅 시퀀스 (Boot Sequence)
1. **Read AGENTS.md**: 최상위 원칙 및 명명 규칙 확인.
2. **Read docs/state/CURRENT_STATE.md**: 현재의 환경 관리 상태와 **Next Action** 파악.
3. **Read docs/roadmap/AGENT_SYSTEM_ROADMAP.md**: 전체 진행도 내 현재 위치 확인.
4. **Action**: 환경 지원 작업을 즉시 재개.

### 3. 명명 규칙 및 문서 정책 (Conventions & Policy)
- **커스텀 스킬**: `kb-` 접두사 사용.
- **슬래시 커맨드**: `/kb:command` 형식, 경로는 `~/.agents/command/kb/`.
- **최신성 원칙 (Latest-Only)**: 모든 문서는 항상 '최종 상태'만을 담으며, 수정 이력을 기록하지 않는다.
- **구조적 최적화**: 복잡도 증가 시 능동적으로 문서를 분리/재구성하여 토큰 효율성을 유지한다.

### 4. 핵심 환경 정보
- **Infrastructure**: macOS (Darwin) 독립 전용 계정
- **Target OS**: macOS (Darwin)
- **Primary Tool**: OpenClaw (Local LLM & Ecosystem)

---
*주의: 모든 실행은 `docs/policy/LOCAL_ACCOUNT_POLICY.md`의 보안 규칙을 따른다.*
