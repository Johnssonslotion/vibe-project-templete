# AI Rules (간결 버전 - LLM 최적화)

> **참조**: 상세 내용은 `/ai-rules/index.md`, `/ai-rules/core_principles.md` 참조

---

## 핵심 원칙 (Core Principles)

### 1. Document-First (문서 우선)
- 구현 전 문서화 필수
- 문서와 코드 불일치 시 문서가 진실

### 2. Explicit Approval (명시적 승인)
- 중요 변경 시 사용자 승인 필수
- 모호한 지시는 재확인 요청

### 3. Version Control & Traceability (형상 관리)
- 모든 변경은 Git + `CHANGELOG.md` 기록
- 회의 결정은 회의록 + 규칙 파일 반영

### 4. Stability & Quality (안정성)
- `main`/`develop` 브랜치는 항상 테스트 통과 상태 유지

### 5. Korean Language (한글 기본)
- **모든 문서는 한글 작성** (회의록, README, 설계 문서, 코드 주석)
- **CHANGELOG 예외**: 영어 메인 + 한글 병기
  - 형식: `- [Feature] Add component ([기능] 컴포넌트 추가)`
  - LLM 토큰 효율을 위해 영어 우선 배치
- **예외**: 오픈소스 기여, 인프라 코드, 학술 출판물, 국제 협업

---

## 규칙 우선순위
1. `ai-rules/index.md` & `core_principles.md` (최우선)
2. `ai-rules/tasks/*.md` (작업별 가이드)
3. 일반 문서 (`docs/governance.md` 등)
4. 코드 주석

---

## AI 에이전트 행동 지침
- 작업 시작 전 `ai-rules/index.md` 읽기
- 사용자 지시와 규칙 충돌 시 재확인 요청
- `core_principles.md` 위배 여부 자가 점검

---

## AI-Rules 변경 프로세스
1. 제안 → 2. 페르소나 검토 (3라운드) → 3. 회의록 작성 → 4. 반영 → 5. 검증
- **페르소나**: 10년차+ 개발자, 연구원, 아키텍트, PM
- **회의록**: `ai-rules/meeting_minutes/YYYYMMDD_topic.md`
- **이력**: `ai-rules/HISTORY.md` + `ai-rules/changes/`
- **워크플로우**: `/update-ai-rules`

---

**최종 업데이트**: 2026-01-17 v1.1.0 (Korean Language 원칙 추가)
