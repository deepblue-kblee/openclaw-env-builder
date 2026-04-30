# 🛠️ OpenClaw CLI 가이드 (Local Env Helper용)

이 가이드는 독립된 macOS 계정 환경에서 OpenClaw를 관리하기 위한 핵심 명령어 모음이다.

---

### 1. 기본 시스템 제어
- **상태 확인**: `openclaw doctor` (환경 설정 및 의존성 점검)
- **버전 확인**: `openclaw --version`
- **도움말**: `openclaw --help`

### 2. 에이전트 및 서비스 관리
- **데몬 실행**: `openclaw start` (백그라운드 서비스 시작)
- **데몬 중지**: `openclaw stop`
- **설정 확인**: `openclaw config list`
- **로그 확인**: `tail -f ~/.openclaw/logs/main.log`

### 3. 스킬 및 명령어 관리
- **스킬 목록**: `openclaw skill list`
- **명령어 실행**: `openclaw run [command_name]`
- **도구 목록**: `openclaw tool list`

### 4. 로컬 환경 유지보수 (Helper 추천)
- **패키지 점검**: `brew doctor` (Homebrew 상태 점검)
- **의존성 업데이트**: `brew update && brew upgrade`
- **Node/Python 관리**: `nvm ls`, `pyenv versions` (버전 격리 상태 확인)

---

### 💡 팁
- 샌드박스가 없으므로 모든 명령은 현재 계정의 쉘에서 직접 실행됩니다.
- 권한 문제가 발생하면 `docs/policy/LOCAL_ACCOUNT_POLICY.md`를 참조하여 sudoers 설정을 점검하십시오.
- `openclaw config edit`를 통해 로컬 LLM 엔드포인트나 모델 설정을 변경할 수 있습니다.
