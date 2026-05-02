# 🤖 OpenClaw Env Helper

이 프로젝트는 맥미니(Mac mini) 서버를 기반으로, AI 에이전트가 로컬 환경에서 다양한 도구를 활용하여 업무를 수행할 수 있도록 **독립된 macOS 계정 환경**을 관리하고 최적화하는 조력자(Helper) 역할을 수행합니다.

## 🌟 주요 목적
- **효율적인 시스템 활용**: 가상화(Docker)의 오버헤드를 없애고 macOS의 네이티브 성능과 API를 직접 활용합니다.
- **보안 및 격리**: 메인 계정과 분리된 **독립된 OS 계정**에서 OpenClaw를 운용하여 데이터를 안전하게 보호합니다.
- **자동화된 환경 관리**: AI 에이전트가 독립 계정 내의 설정, 패키지 관리, 보안 정책을 자동으로 유지관리합니다.

## 🛠️ 기술 스택
- **Infrastructure**: macOS (Darwin) 독립 전용 계정
- **Execution Layer**: OpenClaw (Local LLM & Automation)
- **Management Agent**: Gemini CLI (Environment Helper)

## 📁 프로젝트 구조
- `GEMINI.md`: 에이전트 시스템 루트 가이드 (가장 먼저 읽을 것)
- `docs/state/CURRENT_STATE.md`: 현재 작업 상태 및 다음 액션
- `docs/roadmap/AGENT_SYSTEM_ROADMAP.md`: 전체 프로젝트 구축 로드맵
- `docs/policy/`: 로컬 계정 보안 및 운영 정책
- `deprecated/`: 이전 아키텍처(Sandbox Era) 관련 아카이브

## 🚀 시작하기
1. 사용자가 독립된 macOS 계정을 생성합니다.
2. 해당 계정 공간에 본 저장소를 클론합니다.
3. `GEMINI.md` 지침에 따라 에이전트가 환경 구축 및 관리를 지원합니다.
