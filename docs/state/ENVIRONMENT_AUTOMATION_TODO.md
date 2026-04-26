# 🛠️ 환경 자동화 및 유지보수 가이드 (ENVIRONMENT_AUTOMATION_TODO)

이 문서는 샌드박스 환경의 변동 요소를 효율적으로 관리하기 위한 자동화 계획과 현재의 성공적인 설정 베이스라인을 기록합니다.

---

### 1. 현재 성공 베이스라인 (Current Success Baseline)
현재 자비스가 정상 작동하는 핵심 설정 값입니다. 환경이 꼬였을 때 이 값을 기준으로 복구합니다.
- **Host LAN IP**: `192.168.219.192` (Ollama 연결용)
- **Ollama Port**: `11434`
- **Model**: `qwen2.5:7b`
- **Sandbox Name**: `jarvis-box`
- **Policy Status**: Version 6 (L7 Egress Filtered)
- **핵심 경로**:
  - 설정: `core_harness/openclaw-sandbox.yaml`
  - 정책: `core_harness/openshell-policy.yaml`

---

### 2. 자동화 대상 분석 (Volatile vs Stable)
사용자가 요청 시 즉시 구현해야 할 3대 자동화 대상입니다.

#### **A. [우선순위 1] 네트워크 및 IP 동기화 (`jarvis-network-refresh`)**
- **사유**: 호스트 IP 변경 시 샌드박스 통신 차단(403 Forbidden) 발생.
- **로직**:
  1. 호스트의 `en0` 또는 활성 인터페이스에서 `inet` IP 추출.
  2. `openshell-policy.yaml`의 `llm_api_access` 섹션 내 IP 주소 자동 치환.
  3. `openshell policy set jarvis-box --policy ...` 명령 실행.

#### **B. [우선순위 2] 지능 설정 관리 (`jarvis-brain-setup`)**
- **사유**: 모델 교체나 연결 설정(Base URL) 변경 시 수동 수정 번거로움.
- **로직**:
  1. `openclaw-sandbox.yaml`의 `env` 섹션 데이터를 샌드박스 내부 환경 변수로 동기화.
  2. 필요시 `OPENCLAW_LLM_MODEL` 값만 인터랙티브하게 변경.

#### **C. [우선순위 3] 필수 스킬 설치 자동화 (`jarvis-skill-sync`)**
- **사유**: 환경 재구축 후 수십 개의 스킬을 수동 설치하는 비효율 제거.
- **로직**:
  1. `openclaw-sandbox.yaml`의 `skills.required` 리스트 파싱.
  2. 샌드박스 내부에서 `openclaw skill install [skill-name]` 순차 실행.

---

### 3. 구현 기술 스택 제안
- **Tool**: `Makefile` (맥미니 환경에서 의존성 없이 즉시 실행 가능)
- **Helper**: `jq` 또는 `yq` (YAML/JSON 파싱용)
- **Command Entry**: `make network-sync`, `make brain-setup`, `make skill-sync`

---

### 4. 사용자 지시 대기 상태
"환경 자동화 작업을 시작해줘"라고 요청하면, 이 문서의 **2번 항목**부터 순차적으로 구현을 시작합니다.
