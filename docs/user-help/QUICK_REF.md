# 🚀 OpenClaw Quick Reference (FAQ)

이 문서는 자주 사용하는 명령어와 가이드를 요약한 파일입니다.

## 📌 Index
1. [LLM 모델 관리 (조회/추가/삭제)](#1-llm-모델-관리-조회추가삭제)

---

## 1. LLM 모델 관리 (조회/추가/삭제)

### ✅ 모델 조회
현재 설정된 모델 목록을 확인합니다.
```bash
openclaw models list
```

### ✅ 모델 추가 (자동 동기화)
Ollama에 `pull` 받은 모델을 OpenClaw 대화형 설정을 통해 자동으로 등록합니다.
```bash
# 대화형 메뉴에서 ollama 선택 후 모델 리스트에서 체크
openclaw configure --section model
```

### ✅ 모델 추가 (수동/CLI)
JSON 형식을 사용하여 수동으로 모델을 등록합니다.
```bash
# 1. 모델 정의 (id, contextWindow 등)
openclaw config set --merge models.providers.ollama.models '[{"id": "모델명", "name": "모델명", "contextWindow": 8192, "input": ["text"]}]'

# 2. 에이전트 활성화
openclaw config set --merge agents.defaults.models '{"ollama/모델명": {}}'
```

### ✅ 모델 삭제
특정 모델을 에이전트 사용 목록에서 제거합니다.
```bash
openclaw config unset agents.defaults.models.<MODEL_ID>
# 예: openclaw config unset agents.defaults.models.ollama/gemma
```

### ✅ 기본 모델 설정
기본으로 사용할 모델을 지정합니다.
```bash
openclaw models set <MODEL_ID>
```

---
*새로운 항목이 추가될 때마다 Index를 갱신합니다.*
