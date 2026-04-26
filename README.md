# 🤖 OpenClaw Env Builder

> **"맥미니 기반의 안전하고 자율적인 로컬 에이전트 실행 환경"**

이 프로젝트는 맥미니(Mac mini) 서버를 기반으로, AI 에이전트가 로컬 환경에서 다양한 도구를 활용하여 업무를 수행할 수 있는 보안 격리 환경(Docker Sandbox)과 실행 층(OpenClaw)을 구축합니다.

---

## 🏛️ 주요 특징 및 설계 원칙

- **보안 및 격리 (Sandbox)**: 모든 위험 작업은 **OpenClaw Docker Sandbox** 내부에서 수행되어 호스트 시스템을 안전하게 보호합니다.
- **로컬 중심 (Local-First)**: 외부 의존성을 최소화하고 맥미니의 자원을 효율적으로 활용하는 에이전트 환경을 지향합니다.
- **세션 연속성 (Continuity)**: `CURRENT_STATE.md`를 통해 에이전트가 중단된 지점부터 즉시 작업을 재개할 수 있는 상태 기반 워크플로우를 제공합니다.
- **표준 준수**: 하네스 엔지니어링(Harness Engineering) 원칙에 따라 실수를 방지하는 구조적 시스템 설계를 기본으로 합니다.

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
- `/docs/methodology/`: 보안 정책 및 기술 세부 문서
- `/docs/user-help/`: 빠른 참조 가이드 및 가이드라인

---

## 🚀 에이전트 부팅 시퀀스 (Boot Sequence)

새로운 세션이 시작되면 에이전트는 반드시 다음 순서로 문서를 확인해야 합니다:
1. `AGENTS.md` (원칙 확인)
2. `docs/state/CURRENT_STATE.md` (현재 작업 및 변수 파악)
3. `docs/roadmap/AGENT_SYSTEM_ROADMAP.md` (전체 진행 상황 확인)

---

## 📝 라이선스
이 프로젝트는 개인 개발용 환경 구축 도구입니다.
