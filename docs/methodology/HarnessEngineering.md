# 🧬 하네스 엔지니어링 (Harness Engineering) 핵심 철학

이 문서는 에이전트 시스템의 설계 및 운영을 지배하는 최상위 철학적 기반이다.

---

### 1. 핵심 철학 (Core Philosophy)
- **"인간은 조종하고, 에이전트는 실행한다 (Humans steer. Agents execute.)"**
- **수동 작성 코드 제로 (Zero lines of manually-written code)**: 모든 결과물은 에이전트가 생성하며, 인간은 의도 명시와 피드백 루프 구축에만 집중한다.
- **에이전트 가독성 최우선 (Agent Legibility is the Goal)**: 저장소 외부의 지식은 존재하지 않는 것과 같다. 모든 맥락은 `docs/` 내 문서로 관리하며, 에이전트가 읽기 편한 구조를 유지한다.

### 2. 운영 원칙 (Operating Principles)

1. **엄격한 아키텍처와 제약 (Enforcing Architecture and Taste)**:
   - 구현의 자율성은 주되, 구조적 제약은 문서화된 하네스(AGENTS.md 등)를 통해 기계적으로 강제한다.
2. **점진적 공개 (Progressive Disclosure)**:
   - `AGENTS.md`를 지도로 활용하여, 필요한 시점에만 필요한 상세 문서를 참조하게 하여 토큰 효율성을 극대화한다.
3. **독립 계정 격리 (Local Isolation)**:
   - 샌드박스의 물리적 오버헤드 대신 macOS 계정의 논리적 격리를 활용하여 보안과 성능의 균형을 맞춘다.
4. **지속적인 엔트로피 관리 (Entropy & GC)**:
   - 문서가 커지거나 복잡해지면 능동적으로 분리하고 정리하여 시스템의 '깨끗함'을 유지한다.

---
*참조: OpenClaw Env Helper 프로젝트*
