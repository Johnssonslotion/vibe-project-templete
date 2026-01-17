# Mock-to-Real 개발 워크플로우

상용 품질 확보를 위해 Mock 기반 개발에서 실제 시스템 연동으로 전환하는 절차입니다.

---

## 1. 관련 원칙
- **Principle 11**: Mock-to-Real Development (단계적 진화)

## 2. 단계별 프로세스

### 1단계: 인터페이스 및 실패 모델 정의
- 통신 인터페이스 선언.
- 4xx, 5xx 에러 및 네트워크 지연 시나리오 모델링.

### 2단계: 수동 Mocking 및 테스트 자동화
- `tests/mocks/` 하위에 수동 Mock 구현체 작성.
- Mock이 에러 시나리오를 정상적으로 호출하는지 테스트 코드로 검증.
- **Documentation Expert**: Mock 리스트가 최신 스펙과 일치하는지 검토.

### 3단계: 실제 연동 및 스왑 (Swap)
- Dependency Injection을 통해 구현체를 Real 모듈로 교체.
- 실제 응답 데이터와 Mock 규격의 일치 여부 확인.

### 4단계: 상용 검증 (Production Verification)
- 대규모 부하 및 연속 실패 상황에서 시스템 안정성 최종 확인.

---

## 체크리스트
- [ ] 수동 Mock 리스트 관리 및 테스트 매핑 완료
- [ ] Failure 인젝션(Error Injector) 동작 확인
- [ ] `ai-rules/tasks/development.md` 가이드라인 준수 확인
- [ ] `docs/HISTORY.md` 기록 완료
