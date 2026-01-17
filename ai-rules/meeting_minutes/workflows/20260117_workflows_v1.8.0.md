# AI-Rules 회의록: 워크플로우 거버넌스 및 README 통합 (v1.8.0)

**일시**: 2026-01-17  
**참석자**: [페르소나 기반 검토] Senior Software Engineer, Research Lead, System Architect, Project Manager, Documentation Expert  
**주제**: 거버넌스 워크플로우를 ai-rules 산하로 이동 및 README 통합 가시성 확보

---

## 1. 변경 제안 요약

### 변경 동기 (Why)
`.agent/` 폴더는 AI 시스템의 내부 폴더 성격이 강하므로, 프로젝트 고유의 거버넌스 자산인 워크플로우를 사용자 관리 영역인 `ai-rules/` 산하로 분리하여 관리 투명성을 높임. 또한 사용자가 워크플로우를 쉽게 발견하고 사용할 수 있도록 `README.md`에 통합함.

### 변경 내용 (What)
1. **위치 이동**: `.agent/workflows/` -> `ai-rules/workflows/`.
2. **README 통합**: 전체 워크플로우 목록 및 요약표 추가.
3. **워크플로우 거버넌스**: 전용 `HISTORY.md` 및 `manage-workflows.md` (메타 워크플로우) 도입.
4. **버전 업데이트**: v1.8.0 반영.

### 예상 영향 (Impact)
- **긍정**: 시스템 폴더와 거버넌스 폴더의 명확한 분리, 사용자의 워크플로우 접근성 비약적 향상.
- **부정**: 기존 워크플로우 참조 경로 수정 필요.

---

## 2. 페르소나 검토 (3라운드)

### 라운드 1: 독립 의견

#### Documentation Expert (문서 전문가)
**입장**: 찬성  
**의견**:
- 워크플로우가 `ai-rules/` 폴더로 온 것은 '지식 자산'으로서의 정체성을 확립하는 좋은 조치임.
- `README.md`에서 전체 프로세스를 조망할 수 있게 된 것이 이번 버전의 핵심 가치임.

#### Senior Software Engineer (시니어 개발자)
**입장**: 찬성  
**의견**:
- `.agent/` 폴더는 숨겨진 폴더인 경우가 많아 개발자가 직접 수정하기 부담스러웠는데, `ai-rules/`로 이동하여 수정이 훨씬 편해짐.

#### System Architect (시스템 아키텍트)
**입장**: 찬성  
**의견**:
- 워크플로우를 관리하는 '메타 워크플로우'(`manage-workflows.md`) 도입은 거버넌스 시스템의 자기 완결성을 높여줌.

#### Research Lead (연구 리드)
**입장**: 찬성  
**의견**:
- 연구자들이 거버넌스 워크플로우를 더 쉽게 인지하고 따를 수 있게 됨.

#### Project Manager (프로젝트 매니저)
**입장**: 강력 찬성  
**의견**:
- `README.md` 요약표는 프로젝트 온보딩 시 매우 강력한 가이드가 될 것임.

---

### 라운드 2: 반박 및 보완

#### Documentation Expert
- **보완**: `ai-rules/index.md`에서도 워크플로우 리스트를 참조할 수 있도록 링크를 추가하자.

#### System Architect
- **보완**: `manage-workflows.md`에서 워크플로우의 'turbo' 옵션 사용에 대한 보안 가이드라인도 추후 고려해야 함.

---

### 라운드 3: 최종 입장 및 타협안

#### 전원 찬성
- 경로 이동 및 `README.md` 통합, 워크플로우 전용 히스토리 관리에 전적으로 합의.

---

## 3. PM 최종 보고서

### 합의 사항
- **Directory**: `ai-rules/workflows/`를 거버넌스 실행 도구의 표준 저장소로 확정.
- **Visibility**: `README.md` 최상단 수준에서 워크플로우 가트 제공.
- **Governance**: 워크플로우 변경 역시 페르소나 검토와 히스토리 기록 대상임을 명시.

### 최종 권고
**권고안**: 승인  
**근거**: 시스템(Tooling)과 규칙(Rules)의 분리를 통해 거버넌스의 독립성을 확보하고 사용성을 극대화함.

---

## 4. 합의된 변경 (System Update)

- 거버넌스 워크플로우 7종 이동 및 신규 2종(`HISTORY.md`, `manage-workflows.md`) 생성.
- `README.md` 업데이트 (v1.8.0).
- `docs/HISTORY.md` 및 `ai-rules/HISTORY.md` 업데이트.

---

## 5. 향후 조치 사항 (Action Items)

- [ ] 상세 변경 문서(`changes/`) 작성
- [ ] CHANGELOG.md 반영
- [ ] `.agent/rules/ai-rules.md` 요약본 업데이트
