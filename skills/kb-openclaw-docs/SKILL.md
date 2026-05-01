# 🛠️ Extended Skill: kb-openclaw-docs (Official Manager)

- **Base**: `kb-ai-doc-manager` (Kernel)
- **Spec**: `skills/SKILL_IMPLEMENTATION_PROTOCOL.md`

### 1. 주요 기능 (Capabilities)
- **HTML to Markdown**: 공식 문서 레이아웃을 **Table, Code Block 중심**의 마크다운으로 변환.
- **MVD 처리**: **내비게이션, 푸터, 마케팅 문구** 등 노이즈를 제거하고 순수 기술 정보만 추출.

### 🚀 실행 로직 (Specific Implementation)
본 스킬 실행 시 상위 Kernel과 Spec 규격 문서를 즉시 로드하여 다음 6단계를 수행한다.

1. **Pre-Check**: 로컬 환경(OpenClaw 버전, Node.js, OS) 식별 및 현재 명세와의 대조.
2. **Acquisition**: `web_fetch`를 사용하여 지정된 Scope(**all, setup, config, skills**)의 공식 데이터를 증분 수집.
3. **MVD Logic**: Kernel(`kb-ai-doc-manager`)의 규칙을 적용하여 **기술 명세(Table, Code Block)** 및 **환경 변수/스키마**만 보존.
4. **Structuring**: Spec(`SKILL_IMPLEMENTATION_PROTOCOL.md`)의 L1/L2/L3 구조에 맞춰 콘텐츠 생성.
5. **Validation & Risk**: **설정값/파라미터** 임의 생성 금지, **API 키 노출/sudo/chmod** 감지 시 `⚠️ SECURITY_RISK` 부착.
6. **Approval & Output**: 요약 보고 후 승인 시 **정규화된 텍스트 스트림 또는 임시 파일 경로** 반환. (승인 후 `docs/reference/openclaw/` 반영)

### 2. 제약 사항 (Immutable Constraints)
- **객관성 엄수**: 문서에 없는 파라미터나 설정값을 추측하여 생성하지 않는다.
- **해석 금지**: 모호한 문구는 주관적으로 해석하지 말고 사용자에게 확인을 요청한다.
