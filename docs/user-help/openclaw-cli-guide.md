# 🦞 OpenClaw CLI 관리 가이드

이 문서는 OpenClaw 에이전트 시스템을 관리하기 위한 핵심 명령어를 정리한 요약 가이드입니다.

---

### 1. Gateway 서비스 제어 (Service Control)

서비스 재시작: 설정을 변경한 후 반영할 때 사용합니다.
- openclaw daemon restart
- launchctl kickstart -k gui/$(id -u)/ai.openclaw.gateway (위 명령이 안 될 때)

서비스 상태 확인: 현재 서비스가 정상 작동 중인지 확인합니다.
- openclaw status

실시간 로그 확인: 에이전트 활동 및 오류 로그를 실시간으로 봅니다.
- openclaw logs

---

### 2. 샌드박스 제어 (Sandbox Management)

샌드박스 설정 및 정책 확인: 현재 격리 모드와 허용된 도구 정책을 분석합니다.
- openclaw sandbox explain

실행 중인 샌드박스 목록: 현재 가동 중인 Docker 컨테이너 목록을 확인합니다.
- openclaw sandbox list

샌드박스 강제 재생성: 설정 변경 후 컨테이너를 새로 고칩니다.
- openclaw sandbox recreate --all

---

### 3. 설정 및 환경 관리 (Configuration)

설정 파일 위치 확인: 실제 설정 파일의 경로를 출력합니다.
- openclaw config file

설정 값 조회: 특정 항목의 현재 설정값을 확인합니다.
- openclaw config get models.default
- openclaw config get agents.defaults.sandbox

설정 유효성 검사: JSON 형식 및 필수 키 누락 여부를 체크합니다.
- openclaw config validate

---

### 4. 모델 및 시스템 진단 (Health & Models)

사용 가능한 모델 목록: Ollama 등에서 로드된 모델들을 확인합니다.
- openclaw models list

시스템 종합 진단: 서비스 건강 상태와 연동 이슈를 한꺼번에 점검합니다.
- openclaw doctor

---

### 5. UI 및 대시보드 (Interface)

Control UI 실행: 브라우저에서 관리용 웹 채팅 인터페이스를 엽니다.
- openclaw dashboard

현재 인증 토큰 확인: API 호출이나 외부 연동에 필요한 토큰을 확인합니다.
- openclaw config get gateway.auth.token

---

### 💡 팁
- 채팅 응답이 없거나 이상하면 **openclaw daemon restart**를 먼저 시도하세요.
- 샌드박스 관련 오류는 **openclaw sandbox recreate --all**로 해결되는 경우가 많습니다.
