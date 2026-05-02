# 🚀 OpenClaw Env Helper 구축 마스터 로드맵

**최종 목표**: 독립된 macOS 계정 기반의 안전하고 강력한 OpenClaw 개인용 에이전트 환경 구축 및 관리 지원

---

## 📊 현재 진행 상태
- **현재 단계**: Phase 5. 실무 스킬 고도화 및 시스템 통합 (시작)
- **최근 업데이트**: 2026-05-01
- **전략**: `jarvis` 계정 내에서 시스템 API 및 CLI 도구를 활용한 생산성 극대화

---

## 🛠️ 태스크 체크리스트

### Phase 1: 환경 전환 및 아카이빙 (Done)
- [x] 기존 Docker 샌드박스 관련 파일 격리 (`deprecated/sandbox_era`)
- [x] 샌드박스 정책 문서 아카이빙

### Phase 2: 핵심 문서 재설계 (Done)
- [x] 에이전트 페르소나 변경 (Builder -> Helper)
- [x] `GEMINI.md`, `GEMINI.md` 전면 개편
- [x] 로드맵 및 하네스 방법론 문서 최신화
- [x] `docs/state/CURRENT_STATE.md` 갱신

### Phase 3: 로컬 계정 보안 및 관리 정책 수립 (Done)
- [x] `docs/policy/LOCAL_ACCOUNT_POLICY.md` 작성 (TCC 권한, Sudoers 제어 등)
- [x] 독립 계정 내 OpenClaw 실행 안정성 가이드 작성 (셋업 가이드에 통합)
- [x] 메인 계정 데이터 접근 차단 및 공유 폴더 설정 가이드 (셋업 가이드에 통합)

### Phase 4: 사용자 인수인계 및 초기 셋업 지원 (Done)
- [x] 신규 macOS 계정 생성 가이드 작성 (`docs/setup/NEW_ACCOUNT_SETUP_GUIDE.md`)
- [x] 독립 계정 환경 내 프로젝트 폴더 이전 및 재설정 완료
- [x] 초기 가동 테스트 및 연결 확인 완료

### Phase 5: OpenClaw Core 설치 및 환경 최적화 (In-Progress)
- [ ] (1) OpenClaw CLI 설치 및 바이너리 검증
- [ ] (2) 로컬 LLM 엔드포인트 연동 (Ollama, LM Studio 등) 및 통신 테스트
- [ ] (3) ~/.openclaw 설정 파일 구성 및 커스텀 정책 적용
- [ ] (4) 에이전트-OpenClaw 연동 인터페이스(브릿지) 확인

### Phase 6: 실무 스킬 고도화 및 시스템 통합 (To-Do)
- [x] (1) 시스템 제어 및 자동화 스킬 (`kb-system-ops`)
- [ ] (2) 지정 디렉토리 파일 관리 스킬 (`kb-file-helper`)
- [ ] (3) 로컬 데이터 활용 및 요약 스킬
- [ ] (4) 외부 서비스 API 연동 (내부망 내 안전한 통신)

---

## 📝 변경 이력 (Change Log)
- **2026-05-01**: [Phase 5 진입] `jarvis` 계정으로의 환경 이전 및 검증 완료. 실무 스킬 고도화 단계 착수. ROADMAP 및 CURRENT_STATE 업데이트.
- **2026-04-30**: [전략 대개편] Docker 샌드박스 기반에서 macOS 독립 계정 기반으로 전환. 프로젝트 명칭을 `openclaw-env-helper`로 변경.
- **2026-04-26**: 샌드박스 네트워크 최적화 및 `kb-ai-doc-manager` 스킬 구축 완료.
- **2026-04-13**: 프로젝트 초기화 및 샌드박스 기반 아키텍처 수립.
