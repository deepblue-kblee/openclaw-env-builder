# OpenClaw Native Sandbox 구축 계획 (OpenClaw-Env-Builder)

이 계획은 무겁고 실험적인 NemoClaw 대신 OpenClaw 자체의 Docker 샌드박스 기능을 활용하여 보안과 효율성을 동시에 확보하는 것을 목표로 합니다.

## 1. 샌드박스 아키텍처
- **Backend**: Docker (기본값)
- **Mode**: `all` (모든 세션에 샌드박스 적용)
- **Scope**: `session` (세션당 하나의 컨테이너 유지)
- **보안**: 네트워크 완전 차단 (`network: none`), 루트 파일시스템 읽기 전용 (`readOnlyRoot: true`)

## 2. 단계별 실행 계획

### Phase 1: 샌드박스 환경 설정
- [ ] `openclaw.json` 설정 파일 작성 및 Docker 백엔드 활성화
- [ ] 샌드박스용 전용 Docker 이미지 (`openclaw-sandbox:bookworm-slim`) 빌드 또는 확인
- [ ] 호스트의 API Key 및 설정값 주입 메커니즘 확인 (OpenClaw 기본 기능 활용)

### Phase 2: 업무 지침(Harness) 고도화
- [ ] `AGENTS.md` 및 `GEMINI.md`에서 NemoClaw 관련 지침 제거
- [ ] 샌드박스 내부에서의 파일 I/O 및 툴 사용 가이드라인 수립
- [ ] Zone 2(Sandbox) 실행 시의 자동 라우팅 검증

### Phase 3: 검증 및 테스트
- [ ] 간단한 Python 스크립트 실행을 통한 샌드박스 격리 테스트
- [ ] 네트워크 차단 여부 및 파일시스템 접근 제한 확인
- [ ] 로컬 LLM (Ollama)과의 연동 안정성 테스트

## 3. 주요 변경 사항
- **NemoClaw 삭제**: `nemoclaw onboard`, `openshell` 등 비표준 도구 사용 중단.
- **OpenClaw 표준 준수**: 모든 툴 실행은 OpenClaw Gateway가 직접 관리하는 Docker 컨테이너 내에서 수행.
- **로컬 우선**: 맥미니 서버 자원을 효율적으로 사용하기 위해 경량화된 `slim` 이미지 기반 샌드박스 운영.
