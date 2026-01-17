# AI Rules Change History (Index)

이 문서는 AI Rules 변경의 **요약 이력**을 관리합니다.  
상세 변경 내용은 `ai-rules/changes/` 디렉터리를 참고하세요.

---

---

## [v1.1.0] - 2026-01-17
**변경 주체**: AI-Rules 페르소나 검토 프로세스  
**승인자**: 사용자  
**회의록**: [20260117_korean_language.md](meeting_minutes/20260117_korean_language.md)

### 변경 내용
- Korean Language (한글 기본) 원칙 추가
- 모든 프로젝트 문서는 한글로 작성 기본
- CHANGELOG는 영어 메인 + 한글 병기 (LLM 토큰 효율 및 사용자 편의)
- 예외 조항 명시: 오픈소스, 인프라 코드, 학술 출판물, 국제 협업

### 상세 문서
- [변경 상세: v1.1.0](changes/20260117_v1.1.0_korean_language.md)

---

## [v1.0.0] - 2026-01-17
**변경 주체**: 프로젝트 초기 설정  
**승인자**: 사용자  
**회의록**: [20260117_initial_setup.md](../docs/meeting_minutes/20260117_initial_setup.md)

### 변경 내용
- AI Rules 관리 구조 수립 (`index.md`, `core_principles.md`)
- Document-First, Explicit Approval, Version Control 원칙 정의
- `.agent/rules/ai-rules.md` 자동 동기화 메커니즘 구현

### 상세 문서
- [변경 상세: v1.0.0](changes/20260117_v1.0.0_initial_setup.md)

---

## 변경 이력 작성 규칙
1. 각 변경은 **버전 번호**(Semantic Versioning), **날짜**, **변경 주체**, **승인자**를 명시
2. **회의록 링크** 필수 (합의 근거)
3. 상세 변경 문서는 `ai-rules/changes/YYYYMMDD_vX.Y.Z_description.md` 형식으로 작성
