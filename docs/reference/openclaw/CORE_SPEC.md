# ⚙️ OpenClaw Core Specification (L2)

이 문서는 OpenClaw v2026.4.29 기준의 핵심 기술 명세 및 설치 환경 정의이다.

---

### 1. 설치 환경 (Installation)
- **Runtime**: Node.js 24 (권장) 또는 Node.js 22.14 이상
- **패키지 설치**: `npm install -g openclaw@latest`
- **데몬 설정 (macOS)**: `openclaw onboard --install-daemon` (launchd 서비스 등록)

### 2. 파일 시스템 구조 (Filesystem)
| 경로 | 용도 | 비고 |
| :--- | :--- | :--- |
| `~/.openclaw/openclaw.json` | 전역 설정 파일 | JSON 포맷 |
| `~/.openclaw/workspace/` | 에이전트 작업 공간 | 핵심 로직 포함 |
| `~/.openclaw/workspace/AGENTS.md` | 에이전트 페르소나 정의 | |
| `~/.openclaw/workspace/skills/` | 커스텀 스킬 저장소 | `SKILL.md` 단위 관리 |
| `~/.openclaw/workspace/memory.db` | 장기 기억 저장소 | SQLite |

### 3. 핵심 커맨드 (CLI Commands)
- `openclaw onboard`: 통합 온보딩 (게이트웨이, 워크스페이스, 채널 설정)
- `openclaw gateway`: 게이트웨이 서버 수동 시작
- `openclaw doctor`: 환경 진단 및 보안 체크
- `openclaw pairing approve <channel> <code>`: 신규 채널 페어링 승인

### 4. 보안 정책 (Security)
- **DM Policy**:
  - `pairing` (Default): 알 수 없는 발신자에게 인증 코드 요구
  - `open`: 모든 메시지 수용 (보안 취약점 주의)
- **Sandboxing**: `agents.defaults.sandbox.mode: "non-main"` 설정을 통해 도구 실행 격리 지원.
- **Environment Variables**: `.env` 파일을 통해 API Key 관리.

---
*Ref: [GitHub - openclaw/openclaw](https://github.com/openclaw/openclaw)*
*Tag: #spec, #setup, #security*
