# 🤖 OpenClaw Env Builder

> **"하네스 엔지니어링 원칙에 기반한 고성능 로컬 에이전트 환경 구축"**

이 프로젝트는 맥미니(Mac mini) 서버를 기반으로, AI 에이전트가 안전하고 자율적으로 업무를 수행할 수 있는 보안 격리 환경(Docker Sandbox)과 실행 층(OpenClaw)을 구축하는 것을 목표로 합니다.

---

## 🏛️ 핵심 설계 철학 (Core Philosophy)

### 1. 하네스 엔지니어링 (Harness Engineering)
실수가 발생하면 프롬프트를 수정하는 대신, **시스템 구조(Harness)**를 개선하여 재발을 방지합니다. 에이전트의 자율 주행을 보장하면서도 안전한 가드레일을 제공합니다.

### 2. 로컬 우선 & 보안 격리 (Local-First & Sandbox)
- 모든 위험 작업(외부 코드 실행, 패키지 설치 등)은 **OpenClaw Docker Sandbox** 내부에서 수행됩니다.
- 호스트 시스템과의 철저한 분리를 통해 보안을 강화하고 재현 가능한 환경을 유지합니다.

### 3. 세션 연속성 (Session Continuity)
에이전트가 중단된 지점부터 즉시 작업을 재개할 수 있도록 `CURRENT_STATE.md`와 `AGENTS.md`를 통한 상태 관리를 수행합니다.

---

## 🛠️ 기술 스택 (Tech Stack)

- **Main Agent Layer**: Gemini CLI (Interactive Task Execution)
- **Execution Layer**: OpenClaw (Sandbox & Task Automation)
- **Sandbox**: Docker (openclaw-sandbox:bookworm-slim)
- **Hardware Bridge**: ADB / Scrcpy (Android Automation)
- **Host OS**: macOS (Darwin) on Mac mini

---

## 📂 프로젝트 구조 (Structure)

- `/AGENTS.md`: 에이전트 최상위 행동 지침
- `/docs/state/CURRENT_STATE.md`: 실시간 작업 상태 및 체크포인트
- `/docs/roadmap/AGENT_SYSTEM_ROADMAP.md`: 프로젝트 전체 일정 및 히스토리
- `/docs/methodology/`: 하네스 엔지니어링 및 보안 정책 상세 문서
- `/docs/user-help/`: 사용자 및 에이전트를 위한 빠른 참조 가이드
- `/skills/`: 에이전트 확장 능력(Skills) 저장소

---

## 🚀 에이전트 부팅 시퀀스 (Boot Sequence)

새로운 세션이 시작되면 에이전트는 반드시 다음 순서로 문서를 확인해야 합니다:
1. `AGENTS.md` (원칙 확인)
2. `docs/state/CURRENT_STATE.md` (현재 작업 및 변수 파악)
3. `docs/roadmap/AGENT_SYSTEM_ROADMAP.md` (전체 진행 상황 확인)

---

## 📝 라이선스
이 프로젝트는 개인 개발용 환경 구축 도구입니다.
