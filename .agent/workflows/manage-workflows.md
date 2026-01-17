# 워크플로우 관리 가이드라인 (Meta-Workflow)

이 워크플로우는 프로젝트의 거버넌스를 실행하는 **워크플로우 자체**를 생성, 수정, 폐기할 때 사용됩니다.

---

## 1. 관련 원칙
- **Principle 3**: Version Control & Traceability (형상 관리 및 추적성)
- **Principle 5**: Documentation Expert Review (문서 전문가 검토)

## 2. 단계별 프로세스

### 1단계: 변경 필요성 제안
- 신규 프로세스 도입 또는 기존 워크플로우의 비효율성 발견 시 제안.
- **분리 원칙**: 특정 도구에 종속적인 단계와 보편적인 거버넌스 단계를 구분하여 작성.

### 2단계: 워크플로우 설계 (Technical Writing)
- `ai-rules/workflows/` 내에 마크다운 파일 생성.
- **필수 포함 섹션**:
  - `관련 원칙`: 해당 워크플로우가 준수하는 Core Principle 명시.
  - `단계별 프로세스`: 명확하고 번호가 매겨진 절차.
  - `체크리스트`: 작업 완료 전 자가 점검용 항목.

### 3단계: 전문가 검토 (Peer Review)
- **Documentation Expert**: 구조화, 가독성, 용어 표준화 검토 (필수).
- **Senior Software Engineer**: 실행 가능성 및 자동화(turbo) 가능 여부 검토.

### 4단계: 동기화(Sync) 및 배포
- `ai-rules/workflows/` 하위의 모든 변경 사항은 **`.agent/workflows/`로 즉시 복사**되어야 함.
- 이는 `init_repo.sh` 및 pre-commit 훅을 통해 자동화되지만, AI 에이전트의 즉각적인 인식을 위해 수동 복사(`cp`)를 권장.

### 5단계: 히스토리 및 인덱스 업데이트
- `ai-rules/workflows/HISTORY.md` 기록.
- `README.md`의 워크플로우 요약표 업데이트.
- `docs/HISTORY.md` (마스터 히스토리) 반영.

---

## 체크리스트
- [ ] 워크플로우 파일 상단에 관련 원칙(Core Principle) 명시 완료
- [ ] Documentation Expert의 가독성 승인 획득
- [ ] README.md 요약표에 신규 워크플로우 추가 완료
- [ ] `.agent/rules/ai-rules.md` 요약본 반영
