# Documentation Compliance Workflow

이 워크플로우는 AI 에이전트가 작업을 수행할 때 정의된 **거버넌스 및 문서 체계**를 완벽히 준수하는지 점검합니다.

---

## 1. 점검 대상 (Audit Items)

| 항목 | 준수 기준 | 관련 문서 |
|:---|:---|:---|
| **문서 우선** | 구현 전 설계/명세서 작성이 선행되었는가? | `core_principles.md` |
| **명시적 승인** | 중요 변경 전 사용자의 승인을 받았는가? | `core_principles.md` |
| **계획 및 설계** | RFC(큰 변경) 또는 Spec(기능) 작성이 완료되었는가? | `docs/rfc/`, `specification.md` |
| **Git 전략** | 목적에 맞는 브랜치(`docs/`, `feat/`, `fix/`)를 사용했는가? | `core_principles.md` |
| **이력 관리** | `CHANGELOG.md`, `HISTORY.md`에 기록했는가? | `CHANGELOG.md`, `HISTORY.md` |
| **마스터 히스토리** | `docs/HISTORY.md`에 주요 문서 변경을 기록했는가? | `docs/HISTORY.md` |
| **한글/이중언어** | 문서는 한글, CHANGELOG는 영/한 병기하였는가? | `core_principles.md` |

---

## 2. 자가 점검 프로세스 (Post-Task Audit)

모든 작업을 마친 후, AI는 아래 단계를 자가 수행합니다:

1. **문서 동기화**: `ai-rules/` 변경 시 `.agent/rules/ai-rules.md`를 업데이트했는지 확인.
2. **히스토리 업데이트**: `ai-rules/HISTORY.md`와 `docs/HISTORY.md`가 최신 변경을 반영하는지 확인.
3. **버전 관리**: Semantic Versioning에 따라 적절한 버전을 할당했는지 확인.
4. **브랜치 확인**: 현재 작업이 올바른 feature 브랜치에서 수행되었는지 확인.

---

## 3. 위반 시 조치
- 정의된 원칙과 충돌하는 지시가 있을 경우, 사용자에게 해당 원칙을 상기시키고 재확인을 요청합니다.
- 문서화가 누락된 경우, 구현 전 단계로 돌아가 문서를 먼저 작성할 것을 제안합니다.

---
**최종 업데이트**: 2026-01-17
