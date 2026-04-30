# 🆕 신규 macOS 계정 생성 및 셋업 가이드 (NEW_ACCOUNT_SETUP_GUIDE.md)

OpenClaw를 안전하게 구동하기 위해 별도의 macOS 계정을 생성하고 환경을 설정하는 절차이다.

---

### 1. macOS 계정 생성
1. **시스템 설정** > **사용자 및 그룹**으로 이동한다.
2. **사용자 추가**를 클릭한다.
3. **사용자 유형**: `표준` (권장) 또는 `관리자`를 선택한다.
   - *팁: 보안을 위해 표준 사용자로 생성하고, 필요한 경우에만 sudo 권한을 부여하는 것이 좋다.*
4. **전체 이름/계정 이름**: `openclaw` (또는 원하는 이름)으로 설정한다.

### 2. 보안 및 데이터 격리 설정
1. **메인 계정 데이터 접근 차단**:
   - macOS는 기본적으로 타 계정의 홈 디렉토리 접근을 차단하지만, `/Users/Shared` 폴더를 통해 데이터를 주고받을 수 있도록 설정한다.
2. **TCC 권한 설정**:
   - 신규 계정으로 로그인 후, **시스템 설정** > **개인정보 보호 및 보안**에서 OpenClaw에 필요한 권한(풀 디스크 접근, 손쉬운 사용 등)을 최소한으로 부여한다.

### 3. 개발 환경 초기화 (신규 계정에서 실행)
1. **Homebrew 설치**:
   - `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
2. **필수 도구 설치**:
   - `brew install node python git`
3. **OpenClaw 설치**:
   - `npm install -g @openclaw/cli` (또는 해당 프로젝트의 설치 지침에 따름)

### 4. 프로젝트 저장소 이전
1. 메인 계정의 `openclaw-env-builder` (이제 `openclaw-env-helper`) 폴더를 `/Users/Shared/OpenClaw/` 등으로 복사하거나, 신규 계정에서 직접 git clone한다.
2. 신규 계정에서 해당 폴더로 이동하여 `AGENTS.md`를 읽고 작업을 시작한다.

### 5. SSH 접속 설정 (선택 사항)
- 메인 계정에서 신규 계정으로 편리하게 명령을 내리려면 원격 로그인을 활성화하고 SSH 키를 등록한다.
  - `ssh-copy-id openclaw@localhost`

---

### ✅ 최종 체크리스트
- [ ] 독립된 계정이 생성되었는가?
- [ ] 메인 계정의 민감 데이터가 격리되었는가?
- [ ] Homebrew 및 OpenClaw 기본 도구가 설치되었는가?
- [ ] 본 저장소(Env Helper)가 신규 계정 공간에 위치하는가?
