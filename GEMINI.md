# Gemini CLI Instructions: OpenClaw Env Builder

이 프로젝트에서 작업을 시작하기 전, 반드시 최상위의 `AGENTS.md`를 가장 먼저 읽고 해당 지침을 준수하십시오. 모든 실행 계획은 하네스 엔지니어링 원칙과 보안 정책에 기반해야 합니다.

## 🤖 에이전트 행동 원칙 (Core Mandates)
1. **로컬 우선 (Local-First)**: 가능한 경우 로컬 도구 및 LLM을 우선적으로 활용합니다.
2. **샌드박스 격리 (Sandbox Isolation)**: 위험도가 높은 작업(Zone 2: 외부 코드 실행, 패키지 설치 등)은 반드시 OpenClaw **Docker Sandbox**에서 수행합니다.
   - **자동화**: `openclaw.json` 설정에 따라 모든 도구 실행은 자동으로 샌드박스 컨테이너 내에서 이루어집니다.
   - **보안 정책**: 네트워크 차단 및 읽기 전용 루트 파일시스템 설정을 준수합니다.
3. **하네스 준수**: `AGENTS.md` 및 `docs/methodology/HarnessEngineering.md`에 정의된 구조를 엄격히 따릅니다.
4. **점진적 자동화**: 복잡한 작업은 소단위로 쪼개어 검증하며, `docs/state/CURRENT_STATE.md`를 즉시 갱신합니다.

## 🧭 자율 주행 및 개입 프로토콜 (Guided Autonomy Protocol)
무한 루프 방지와 토큰 효율성을 위해 다음 규칙을 준수합니다.
1. **사전 검증 (Verification First)**: 작업을 시작하기 전, 필요한 도구나 의존성이 실제로 존재하는지 확인합니다. (예: Docker 데몬 가동 여부 확인)
2. **상태 기반 진행**: `docs/roadmap/AGENT_SYSTEM_ROADMAP.md`와 `docs/state/CURRENT_STATE.md`를 모든 행동의 '단일 진실 공급원'으로 삼습니다.
3. **사용자 개입 필수 시점**: 에이전트는 다음 상황에서 반드시 작업을 멈추고 사용자에게 지시를 요청해야 합니다.
   - **단계 전환 (Phase Transition)**: 한 Phase를 완료하고 다음 Phase로 넘어가기 직전.
   - **반복 실패**: 동일한 명령이나 논리적 단계가 **3회 연속 실패**할 경우.
   - **파괴적 작업**: 컨테이너 삭제, 호스트 시스템 설정 변경 등 되돌리기 어려운 작업 수행 시.
   - **전략적 모호성**: 로드맵에 명시되지 않은 도구나 프레임워크 선택이 필요할 때.

## 🛠️ 주요 환경 정보
- **OS**: macOS (Darwin) - 맥미니 서버 기반
- **Sandbox Backend**: Docker (OpenClaw Native)
- **Policies**: `docs/policy/SANDBOX_POLICY.md` 참조
