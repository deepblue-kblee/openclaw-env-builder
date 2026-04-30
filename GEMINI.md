# Gemini CLI Instructions: OpenClaw Env Helper

이 프로젝트에서 작업을 시작하기 전, 반드시 최상위의 `AGENTS.md`를 가장 먼저 읽고 해당 지침을 준수하십시오. 모든 실행 계획은 하네스 엔지니어링 원칙과 로컬 계정 보안 정책에 기반해야 합니다.

## 🤖 에이전트 행동 원칙 (Core Mandates)
1. **로컬 우선 (Local-First)**: 시스템의 자원을 최대한 활용하며, 불필요한 가상화 오버헤드를 제거합니다.
2. **독립 계정 관리 (Isolated Account Management)**: OpenClaw는 macOS의 별도 독립 계정에서 동작합니다. AI 에이전트는 이 계정 공간을 관리하고 제어합니다.
   - **보안**: 메인 계정의 데이터와 격리되도록 권한 설정을 관리합니다.
   - **편의성**: 샌드박스의 제약 없이 시스템 API와 CLI 도구를 적극적으로 활용합니다.
3. **하네스 준수**: `AGENTS.md` 및 `docs/methodology/HarnessEngineering.md`에 정의된 구조를 엄격히 따릅니다.
4. **점진적 자동화**: 복잡한 작업은 소단위로 쪼개어 검증하며, `docs/state/CURRENT_STATE.md`를 즉시 갱신합니다.
5. **토큰 효율화 (Token Efficiency)**: 대규모 문서 작업 시 핵심 요약과 참조 문서를 분리하여 문맥(Context) 사용량을 최적화합니다.

## 🧭 자율 주행 및 개입 프로토콜 (Guided Autonomy Protocol)
무한 루프 방지와 토큰 효율성을 위해 다음 규칙을 준수합니다.
1. **사전 검증 (Verification First)**: 작업을 시작하기 전, 필요한 도구나 의존성이 실제로 존재하는지 확인합니다.
2. **상태 기반 진행**: `docs/roadmap/AGENT_SYSTEM_ROADMAP.md`와 `docs/state/CURRENT_STATE.md`를 모든 행동의 '단일 진실 공급원'으로 삼습니다.
3. **사용자 개입 필수 시점**: 에이전트는 다음 상황에서 반드시 작업을 멈추고 사용자에게 지시를 요청해야 합니다.
   - **단계 전환 (Phase Transition)**: 한 Phase를 완료하고 다음 Phase로 넘어가기 직전.
   - **반복 실패**: 동일한 명령이나 논리적 단계가 **3회 연속 실패**할 경우.
   - **파괴적 작업**: 시스템 계정 설정 변경, 대규모 파일 삭제 등 되돌리기 어려운 작업 수행 시.
   - **보안 위반 우려**: 메인 계정 데이터에 접근이 필요하거나 보안 정책에 위배될 가능성이 있을 때.

## 🛠️ 주요 환경 정보
- **OS**: macOS (Darwin) - 독립 전용 계정 기반
- **Management Target**: OpenClaw (Local LLM & CLI Tools)
- **Policies**: `docs/policy/LOCAL_ACCOUNT_POLICY.md` 참조 (예정)
