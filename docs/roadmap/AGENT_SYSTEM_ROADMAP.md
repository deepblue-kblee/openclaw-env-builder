# 🚀 에이전트 시스템 구축 마스터 로드맵

**최종 목표**: 장피엠의 에이전트 전환기 철학을 반영한 고성능 로컬 에이전트 환경 구축 (맥미니 서버 기반)

---

## 📊 현재 진행 상태
- **현재 단계**: Phase 3. 업무 층 (Gemini CLI) 통합 (진행 중)
- **최근 업데이트**: 2026-04-13
- **전략**: 선택적 격리 (Zone 0/1: 호스트, Zone 2: 샌드박스)

---

## 🛠️ 태스크 체크리스트

### Phase 1: 기반 아키텍처 설계 및 하네스 구축 (Done)
- [x] 전체 시스템 폴더 구조 규칙 확정 (`root/`, `agents/`, `skills/` 등)
- [x] 핵심 하네스 문서 작성 (`AGENTS.md`)
- [x] 샌드박스 실행 정책 수립 (`docs/policy/SANDBOX_POLICY.md`)
- [x] 하네스 엔지니어링 방법론 요약본 저장 (`docs/methodology/HarnessEngineering.md`)

### Phase 2: 샌드박스 및 실행 층 구축 (Done)
- [x] Docker Desktop 4.40+ 및 Node.js v22+, Python 점검 완료
- [x] NVIDIA NemoClaw 인스톨러 실행 및 가동
- [x] OpenClaw 샌드박스 컨테이너 구성 및 네트워크 프록시 설정
- [x] 샌드박스용 Credential Injection (API Key 관리) 설정
- [x] 샌드박스 환경 내 테스트 명령 실행 및 로그 검증

### Phase 3: 업무 층 (Gemini CLI) 통합 (In-Progress)
- [x] Gemini CLI 활용 샌드박스 격리 지침(`GEMINI.md`) 수립
- [x] Jarvis 라우팅 가이드 명시 (`openshell sandbox exec`)
- [ ] **[Next]** 샌드박스 내부 OpenClaw CLI 검증 및 기본 스킬 패키지 설치
- [ ] 샌드박스 내 로컬 에이전트(Jarvis) 테스트 시나리오 실행

### Phase 4: 일상/실행 층 (OpenClaw) 확장
- [ ] 안드로이드 공기계 + ADB/Scrcpy 연결
- [ ] 카카오톡 아카이빙 시나리오 구현
- [ ] KTX/열차 조회 자동화 스크립트 작성

### Phase 5: 통합 인터페이스 및 자동화 루프
- [ ] 텔레그램 봇 API 연동 및 브릿지 스크립트(`gatekeeper.py`) 작성
- [ ] 오토 리서치(Auto-Research) 검증 루프 구현
- [ ] 24시간 가동 서버 안정화 테스트

---

## 📝 변경 이력 (Change Log)
- **2026-04-13**: [전략 결정] 초기 구축은 통합형(Method A)으로 진행하되, 설정 완성 후 빌더-배포형(Method B)으로 분리하기로 결정. Phase 2.5 로드맵 추가.
- **2026-04-13**: [Git] 로컬 Git 저장소 초기화 (`openclaw-env-builder`).
- **2026-04-13**: Claude Code 대신 Gemini CLI를 주 업무 층으로 선택. 샌드박스 내부 OpenClaw 초기화 단계 추가. 자율 주행 프로토콜 도입.
- **2026-04-13**: Phase 2 샌드박스 구축 완료 (`jarvis-box` 및 로컬 LLM 연결). Phase 3 업무 층 통합 개시.
- **2026-04-12**: 샌드박스 실행 규칙 수립 및 선택적 격리 전략 채택.
- **2026-04-12**: 프로젝트 로드맵 문서 생성 및 인프라 점검 완료 (Docker v29.3, Node v24.1, Python 3.9).
- **2026-04-12**: 문서 구조 재편성 (docs/ 폴더 하위로 이동) 및 세션 연속성 설계 적용.

---

## ⚠️ 리스크 관리
- **리소스**: 샌드박스 다중 구동 시 맥미니 RAM 부족 가능성 → 스왑 영역 확장 검토 필요.
- **보안**: 샌드박스 우회(Escape) 취약점 모니터링 → 주기적인 NemoClaw 업데이트 필수.
- **루프 방지**: 에이전트의 반복 실패 시 사용자 개입 프로토콜 엄격 적용.
 엄격 적용.
