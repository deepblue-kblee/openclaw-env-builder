# 🛠️ Skill: kb-openclaw-docs (Official Documentation Manager)

이 스킬은 OpenClaw 공식 문서를 가져와 `DOCUMENTATION_STANDARDS.md` 규격에 맞춰 정규화된 데이터로 변환하는 역할을 수행한다.

---

### 1. 주요 기능 (Capabilities)
- **HTML to Markdown 변환**: 공식 문서의 레이아웃을 기술 명세(Table, Code Block) 중심의 마크다운으로 변환.
- **데이터 정규화**: `docs/reference/openclaw/` 구조에 맞게 L1/L2/L3로 데이터 분할.
- **MVD 처리**: 순수 기술 정보 외의 노이즈(내비게이션, 푸터, 마케팅 문구) 제거.

### 2. 실행 로직 (Logic)
1. **Input**: 공식 문서 URL 또는 특정 섹션 식별자 수신.
2. **Extraction**: `web_fetch` 등을 통해 원문 데이터 수집.
3. **MVD & Tagging**: 기술 명세만 추출하고, 각 정보에 `target_version` 및 `source_url` 태그 부여.
4. **Structuring**: `DOCUMENTATION_STANDARDS.md` 기준에 따라 Index, Spec, Guide 파일 내용 생성.
5. **Output**: 정규화된 텍스트 스트림 또는 임시 파일 경로 반환.

### 3. 제약 사항 (Constraints)
- **객관성 엄수**: 공식 문서에 명시되지 않은 설정값이나 파라미터는 절대 임의로 생성하지 않는다.
- **해석 금지**: 모호한 문구는 주관적으로 해석하여 기록하지 않고, 반드시 사용자에게 확인을 요청한다.
- **보안 감지**: `sudo`, `chmod`, API 키 노출 등 보안 위험이 있는 명령어 포함 시 별도의 경고 태그(`⚠️ SECURITY_RISK`)를 추가한다.

### 4. /kb:oc-update 커맨드 워크플로우
- `/kb:oc-update [scope]` 명령 시 본 스킬이 호출된다.
- **Scope 예시**: `all`, `setup`, `config`, `skills`.
- 스킬은 결과물을 즉시 반영하지 않고, **사용자 승인 대기 상태**로 요약 보고서를 먼저 출력한다.
