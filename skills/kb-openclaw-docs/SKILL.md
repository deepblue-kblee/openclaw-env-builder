# 🛠️ Extended Skill: kb-openclaw-docs (Official Manager)

- **Base**: `kb-ai-doc-manager` (Kernel)
- **Spec**: `skills/SKILL_IMPLEMENTATION_PROTOCOL.md`

---

### 🚀 실행 로직 (Specific Implementation)
본 스킬 실행 시 상위 Kernel과 Spec 규격 문서를 즉시 로드하여 다음 6단계를 수행한다.

1. **Pre-Check**: 로컬 환경(OpenClaw 버전, Node.js, OS) 식별 및 현재 명세와의 대조.
2. **Acquisition**: `web_fetch`를 사용하여 지정된 Scope(setup, config 등)의 공식 데이터를 증분 수집.
3. **MVD Logic**: Kernel(`kb-ai-doc-manager`)의 규칙을 적용하여 기술 명세(Table, Code Block)만 보존.
4. **Structuring**: Spec(`SKILL_IMPLEMENTATION_PROTOCOL.md`)의 L1/L2/L3 구조에 맞춰 `INDEX.md`, `CORE_SPEC.md`, `GUIDE_*.md` 콘텐츠 생성.
5. **Validation & Risk**: `target_version` 대조 및 위험 명령어(sudo 등) 감지 시 `⚠️ SECURITY_RISK` 부착.
6. **Approval**: 변경 사항 요약 보고 후 **사용자 최종 승인 대기**. (승인 후 `docs/reference/openclaw/` 반영)
