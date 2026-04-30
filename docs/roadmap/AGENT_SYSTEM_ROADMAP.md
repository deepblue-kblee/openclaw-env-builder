# 🚀 OpenClaw Env Helper 구축 마스터 로드맵

**최종 목표**: 독립된 macOS 계정 기반의 안전하고 강력한 OpenClaw 개인용 에이전트 환경 구축 및 관리 지원

---

## 📊 현재 진행 상태
- **현재 단계**: Phase 2. 핵심 문서 재설계 (진행 중)
- **최근 업데이트**: 2026-04-30
- **전략**: macOS 계정 격리 기반의 적극적 시스템 활용

---

## 🛠️ 태스크 체크리스트

### Phase 1: 환경 전환 및 아카이빙 (Done)
- [x] 기존 Docker 샌드박스 관련 파일 격리 (`deprecated/sandbox_era`)
- [x] 샌드박스 정책 문서 아카이빙

### Phase 2: 핵심 문서 재설계 (In-Progress)
- [x] 에이전트 페르소나 변경 (Builder -> Helper)
- [x] `GEMINI.md`, `AGENTS.md` 전면 개편
- [ ] 로드맵 및 하네스 방법론 문서 최신화
- [ ] `docs/state/CURRENT_STATE.md` 갱신

### Phase 3: 로컬 계정 보안 및 관리 정책 수립
- [ ] `docs/policy/LOCAL_ACCOUNT_POLICY.md` 작성 (TCC 권한, Sudoers 제어 등)
- [ ] 독립 계정 내 OpenClaw 실행 안정성 가이드 작성
- [ ] 메인 계정 데이터 접근 차단 및 공유 폴더 설정 가이드

### Phase 4: 사용자 인수인계 및 초기 셋업 지원
- [ ] 신규 macOS 계정 생성 가이드 작성 (`docs/setup/NEW_ACCOUNT_SETUP_GUIDE.md`)
- [ ] 독립 계정 환경 내 프로젝트 폴더 이전 및 재설정 지원
- [ ] 초기 가동 테스트 및 연결 확인

### Phase 5: 실무 스킬 고도화 및 시스템 통합
- [ ] (1) 시스템 제어 및 자동화 스킬 (`kb-system-ops`)
- [ ] (2) 지정 디렉토리 파일 관리 스킬 (`kb-file-helper`)
- [ ] (3) 로컬 데이터 활용 및 요약 스킬
- [ ] (4) 외부 서비스 API 연동 (내부망 내 안전한 통신)

---

## 📝 변경 이력 (Change Log)
- **2026-04-30**: [전략 대개편] Docker 샌드박스 기반에서 macOS 독립 계정 기반으로 전환. 프로젝트 명칭을 `openclaw-env-helper`로 변경. 불필요한 가상화 오버헤드 제거 및 시스템 활용성 극대화 결정.
- **2026-04-26**: 샌드박스 네트워크 최적화 및 `kb-ai-doc-manager` 스킬 구축 완료.
- **2026-04-13**: 프로젝트 초기화 및 샌드박스 기반 아키텍처 수립.
