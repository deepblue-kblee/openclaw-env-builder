# 🧠 Kernel: kb-ai-doc-manager (Base Document Skill)

이 스킬은 프로젝트 내 모든 문서 작업의 **Ground Rule**과 **공통 기능**을 정의하며, 하위 스킬의 부모 객체 역할을 수행한다.

## 🛠️ 공통 기능 (Base Methods)
- **summarize**: [상태/결과/장애원인] 중심의 3라인 고밀도 요약 생성. (서술형 배제)
- **archive**: 3세션 이상 지난 데이터나 폐기 계획을 즉시 `docs/archives/`로 격리.
- **audit-token**: 문서 내 중복, 인사말, 배경 설명을 식별하여 토큰 소모를 줄이기 위해 제거.

## 🧭 문서 관리 트리거 (Trigger Protocol)
- **Phase 전환**: 로드맵 단계 변경 시 요약본 생성 및 이전 단계 아카이빙.
- **반복 오류**: 동일 오류 3회 발생 시 구조적 대책(`docs/methodology/`) 수립 유도.
- **세션 체크포인트**: 세션 종료 전 `CURRENT_STATE.md`를 1000토큰 이내로 정제.

## ⚠️ 핵심 원칙
- **Latest-Only**: 수정 이력 없이 최종 상태만 유지.
- **No-Filler**: 기술적 사실에만 집중하며 모든 수식어 배제.
- **Inherent Authority**: 본 스킬의 규칙은 모든 도메인 문서 작업의 최상위 그라운드 룰이다.
