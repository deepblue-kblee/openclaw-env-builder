# 📍 현재 작업 상태 (CURRENT_STATE.md)

이 파일은 세션 중단 시 에이전트가 작업을 즉시 재개하기 위한 '체크포인트' 역할을 한다.

---

### 🕒 마지막 업데이트: 2026-04-13
- **현재 진행 단계**: Phase 3. 업무 층 (Gemini CLI) 통합 - 샌드박스 설정 최적화
- **현재 집중 작업 (Current Task)**: 로컬 Ollama 환경에 맞춘 `openclaw-sandbox.yaml` 및 `openshell-policy.yaml` 정밀 튜닝
- **전략적 결정**: 
  - **초기 통합(Method A)**: 현재 빌더 공간에서 모든 설정을 완성.
  - **추후 분리(Method B)**: 설정이 안정화되면 `~/jarvis-home` 등으로 배포하는 구조로 전환.
  - **유지보수 자동화**: 변동성이 높은 설정(IP, 모델, 스킬) 관리를 위한 별도 계획 수립 (`docs/state/ENVIRONMENT_AUTOMATION_TODO.md` 참조).
- **마지막 성공 액션 (Last Action)**: 로컬 Ollama LAN IP 연결 성공 및 정책 v6 적용
- **주요 장애물 (Blockers)**: 
  1. `nemoclaw onboard` 실행 시 `NVIDIA_API_KEY` 필수 요구 (클라우드 NIM 설정 단계).
  2. `openshell` 기본 정책이 외부 통신(npm/clawhub)을 차단하여 스킬 설치 실패 (403 Forbidden).

---

### 💾 임시 컨텍스트 변수
- **Sandbox Name**: jarvis-box
- **Model**: qwen2.5:7b (via Ollama)
- **Harness Config**: `core_harness/openclaw-sandbox.yaml`
- **Policy Config**: `core_harness/openshell-policy.yaml`
- **Next Step In-depth**: 
  - 방법 A: 사용자가 `nemoclaw onboard`를 수동 실행하여 환경 승인.
  - 방법 B: `NVIDIA_API_KEY`를 더미로 입력하여 온보딩 통과 시도.
  - 방법 C: `openshell settings`를 통해 네트워크 정책을 강제 허용으로 수정.
