# AI-Rules 회의록: 개발 아웃라인 고도화 (Mock-to-Real)

**일시**: 2026-01-17  
**참석자**: [페르소나 기반 검토] Senior Software Engineer, Research Lead, System Architect, Project Manager  
**주제**: 수동 Mocking 기반의 Mock-to-Real 개발 전략 수립

---

## 1. 변경 제안 요약

### 변경 동기 (Why)
백엔드 연동 전 UI/로직 개발의 속도를 높이고, 상용 환경에서 발생할 수 있는 다양한 예외 상황(Failure)을 초기 단계부터 견고하게 처리하기 위함. 도구 중립적인 수동 Mocking을 통해 제어력을 극대화함.

### 변경 내용 (What)
1. **Mock-to-Real 4단계 아웃라인**: Interface Modeling -> Manual Mocking -> Real-Flow Transition -> Production Verification.
2. **수동 Mocking 관리**: Mock 리스트 관리 및 테스트 케이스 매핑 필수화.
3. **Failure 관리**: 에러 인젝션 및 실패 시나리오 재현 기능 포함.

### 예상 영향 (Impact)
- **긍정**: 기능 개발과 인프라 개발의 병렬화, 상용 수준의 에러 처리 능력 확보.
- **부정**: Mock 구현 및 관리 비용 발생.

---

## 2. 페르소나 검토 (3라운드)

### 라운드 1: 독립 의견

#### Senior Software Engineer (시니어 개발자)
**입장**: 찬성  
**의견**:
- 특정 Mock 라이브러리를 쓰지 않고 수동으로 인터페이스를 구현하는 방식은 유연성 면에서 최고임.
- 특히 Failure 조작 기능이 있으면 개발 중에 네트워크 에러 팝업 등을 쉽게 테스트할 수 있음.

#### Research Lead (연구 리드)
**입장**: 찬성  
**의견**:
- 연구용 파이프라인에서도 외부 API 호출이 많음. 이를 Mocking 하면 연구 모델의 입력값 변화를 제어하기 쉬워짐.
- Mock 데이터 리스트를 관리하면 어떤 실험이 Mock 기반이었는지 나중에 추적하기 좋음.

#### System Architect (시스템 아키텍트)
**입장**: 강력 찬성  
**의견**:
- Interface-Driven Development의 정수임. 추후 실제 DB나 API로 교체할 때 DI 패턴만 잘 잡혀있으면 코드 수정이 거의 없을 것임.
- 상용 환경을 대비해 "네트워크 타임아웃" 시나리오를 반드시 포함해야 함.

#### Project Manager (프로젝트 매니저)
**입장**: 찬성  
**의견**:
- 백엔드 완료를 기다리지 않고 프론트엔드 기능을 완료할 수 있어 일정 관리가 용이함.
- 테스트 케이스가 Mock과 매핑되면 기능 완성도 증명에 유리함.

---

### 라운드 2: 반박 및 보완

#### Senior Software Engineer
- **보완**: Mock 구현체가 비대해지지 않도록, 필요한 데이터만 정의하는 'Minimal Mocking' 원칙을 추가하자.

#### System Architect
- **보완**: 실제 연동 단계에서 Mock과 Real 데이터 규격이 어긋나는 것을 방지하기 위해, 데이터 스키마 유효성 검사(Contract Testing 등)를 권장사항으로 넣자.

#### Research Lead
- **보완**: 연구 데이터의 경우 Mocking보다는 실제 데이터의 일부(Subset)를 활용하는 패턴도 가이드에 포함하면 좋겠음.

---

### 라운드 3: 최종 입장 및 타협안

#### Senior Software Engineer
**최종 입장**: 찬성  
- 수동 Mocking 및 Failure 관리 가이드라인 확정.

#### System Architect
**최종 입장**: 찬성  
- 상용 수준의 에러 케이스를 포함한 4단계 전환 프로세스 지지.

#### Project Manager
**최종 입장**: 찬성  
- Mock 리스트 관리를 통해 투명한 진행 상황 파악 가능.

---

## 3. PM 최종 보고서

### 합의 사항
- **통제된 Mocking**: 수동으로 인터페이스를 구현하며, Mocking 리스트를 통해 가시성을 확보함.
- **에러 우선 설계**: 성공 케이스만큼이나 실패 시나리오(Failure) 정의에 공수를 들임.
- **검증**: Mock 기반 테스트가 실제 연동 후에도 회귀 테스트로 활용될 수 있도록 설계함.

### 최종 권고
**권고안**: 승인  
**근거**: 프로젝트 초기부터 상용 수준의 예외 처리를 고려하고, 개발 병목을 해소하는 Mock-to-Real 전략은 대규모 상용 프로젝트에 필수적임.

---

## 4. 합의된 변경 (System Update)

- `ai-rules/core_principles.md` 업데이트:
  - **11. Mock-to-Real Development (개발 아웃라인)**: 상용 중심의 단계적 개발 및 Mock 관리 원칙 추가.
- 버전: v1.6.0
- 적용 범위: 신규 기능 개발 및 외부 시스템 연동 전 과정.

---

## 5. 향후 조치 사항 (Action Items)

- [ ] `core_principles.md` (v1.6.0) 수정
- [ ] `ai-rules/tasks/development.md` 작성 완료 (v1.0.0)
- [ ] `ai-rules/HISTORY.md` 및 `docs/HISTORY.md` 기록
- [ ] `.agent/rules/ai-rules.md` 및 `CHANGELOG.md` 반영
