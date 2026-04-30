# Claude Instructions: OpenClaw Env Helper

이 프로젝트에서 작업을 시작하기 전, 반드시 최상위의 `AGENTS.md`를 가장 먼저 읽고 해당 지침을 준수하십시오. 모든 실행 계획은 하네스 엔지니어링 원칙과 로컬 계정 보안 정책에 기반해야 합니다.

## 🤖 에이전트 행동 원칙 (Core Mandates)
1. **로컬 우선 (Local-First)**: 시스템의 자원을 최대한 활용하며, 불필요한 가상화 오버헤드를 제거합니다.
2. **독립 계정 관리 (Isolated Account Management)**: OpenClaw는 macOS의 별도 독립 계정에서 동작합니다. AI 에이전트는 이 계정 공간을 관리하고 제어합니다.
   - **보안**: 메인 계정의 데이터와 격리되도록 권한 설정을 관리합니다.
   - **편의성**: 시스템 API와 CLI 도구를 직접 활용하여 생산성을 높입니다.
3. **하네스 준수**: `AGENTS.md` 및 `docs/methodology/HarnessEngineering.md`에 정의된 구조를 엄격히 따릅니다.
4. **점진적 자동화**: 복잡한 작업은 소단위로 쪼개어 검증하며, `docs/state/CURRENT_STATE.md`를 즉시 갱신합니다.

## 🧭 자율 주행 및 개입 프로토콜 (Guided Autonomy Protocol)
1. **사전 검증 (Verification First)**: 작업을 시작하기 전, 필요한 도구나 의존성이 실제로 존재하는지 확인합니다.
2. **상태 기반 진행**: `docs/roadmap/AGENT_SYSTEM_ROADMAP.md`와 `docs/state/CURRENT_STATE.md`를 모든 행동의 '단일 진실 공급원'으로 삼습니다.
3. **사용자 개입 필수 시점**: 에이전트는 단계 전환, 반복 실패(3회), 파괴적 작업 수행 시 반드시 작업을 멈추고 사용자에게 지시를 요청해야 합니다.

## 🛠️ 주요 환경 정보
- **OS**: macOS (Darwin) - 독립 전용 계정 기반
- **Management Target**: OpenClaw (Local LLM & CLI Tools)
- **Policies**: `docs/policy/LOCAL_ACCOUNT_POLICY.md` 참조
