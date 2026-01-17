# RFC (Request for Comments) 작성 워크플로우

아키텍처 변경, 신규 기술 도입 등 영향도가 큰 결정 전 의견 수렴을 위해 사용됩니다.

---

## 1. 관련 원칙
- **Principle 8**: Plan & Discuss (RFC 프로세스)
- **Principle 9**: Git & Workflow (PR 기반 합의)

## 2. 단계별 프로세스

### 1단계: 초안 작성 (Draft)
- `docs/rfc/template.md`를 복사하여 `docs/rfc/YYYYMMDD_topic.md` 파일 생성.
- 요약, 동기, 상세 설계, 제약 사항을 기록.

### 2단계: 피드백 수집 (Review)
- 관련 페르소나들로부터 기술적 타당성 검토를 받음.
  - **System Architect**: 구조적 무결성 검토.
  - **Senior Software Engineer**: 구현 가능성 검토.
  - **Documentation Expert**: 명세의 명확성 검토.

### 3단계: 합의 및 승인 (Approved)
- 제안된 대안들 중 최적안을 선택하고 상태를 `Approved`로 변경.
- 최종 RFC 내용을 바탕으로 `Specification` 단계로 전환.

---

## 체크리스트
- [ ] RFC 제목 및 메타데이터(상태, 날짜) 작성
- [ ] 실패/부작용(Drawbacks) 섹션 포함 여부
- [ ] 아키텍처 다이아그램(Mermaid) 포함 권장
