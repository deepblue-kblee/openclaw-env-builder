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
  1. `nemoclaw onboard` 시 API Key 요구 (더미 키 또는 직접 설정 우회 필요).

---

### 💾 임시 컨텍스트 변수
- **Sandbox Name**: jarvis-box
- **Model**: qwen2.5:7b (via Ollama)
- **Harness Config**: `core_harness/openclaw-sandbox.yaml`
- **Policy Config**: `core_harness/openshell-policy.yaml`

---

### 🚀 다음 세션 시작 지점 (Next Session Entry Point)
새 세션이 시작되면 에이전트에게 다음 중 하나를 지시하십시오:
1.  **환경 자동화 구현**: `docs/state/ENVIRONMENT_AUTOMATION_TODO.md`의 계획에 따라 `Makefile` 기반 자동화 도구 구축.
2.  **스킬 설치 및 검증**: `core_harness/openclaw-sandbox.yaml`에 정의된 `required` 스킬들을 샌드박스에 실제 설치.
3.  **자비스 시나리오 테스트**: 로컬 LLM을 연동하여 샌드박스 내부에서 자비스의 첫 명령 수행 테스트.
