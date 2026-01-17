# CHANGELOG.md

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Unreleased

### Fixed
- [AI-Rules v1.8.1] Implemented Dual-Location Workflow Strategy ([AI-규칙 v1.8.1] 워크플로우 이중 위치 동기화 전략 도입)
  - Workflows are now managed in `ai-rules/workflows/` and auto-deployed to `.agent/workflows/` for functionality ([거버넌스는 ai-rules에서, 기능은 .agent에서 수행하도록 동기화])
  - Updated `init_repo.sh` and pre-commit hook to automate mirrored deployment ([init_repo.sh 및 훅을 통한 자동 배포 시스템 구축])

### Changed
- [AI-Rules v1.8.0] Enhanced Workflow Governance and README integration ([AI-규칙 v1.8.0] 워크플로우 거버넌스 강화 및 README 통합)
  - Relocated workflows from `.agent/workflows/` to `ai-rules/workflows/` ([워크플로우를 ai-rules/workflows/로 이동하여 관리 투명성 확보])
  - Added workflow summary table to `README.md` for better visibility ([README.md에 워크플로우 요약표 추가 및 가시성 강화])
  - Established dedicated Workflow History and Management (Meta) Workflow ([워크플로우 전용 히스토리 및 관리 워크플로우 도입])
  - Meeting: [20260117_workflows_v1.8.0.md](ai-rules/meeting_minutes/workflows/20260117_workflows_v1.8.0.md)
- [AI-Rules v1.7.0] Modularized Governance Workflows and introduced Documentation Expert persona ([AI-규칙 v1.7.0] 거버넌스 워크플로우 모듈화 및 문서 전문가 페르소나 도입)
  - Split governance processes into 5 independent workflows in `.agent/workflows/` ([거버넌스 프로세스를 5종의 독립된 워크플로우로 분리])
  - Added `Documentation Expert` persona for high-quality knowledge management ([고품질 지식 관리를 위한 '문서 전문가' 페르소나 추가])
  - Updated `/update-ai-rules` to reflect new review standards ([새로운 검토 표준을 반영한 /update-ai-rules 고도화])
  - Meeting: [20260117_workflows_v1.7.0.md](ai-rules/meeting_minutes/workflows/20260117_workflows_v1.7.0.md)
- [AI-Rules v1.6.0] Introduced Mock-to-Real Development Strategy ([AI-규칙 v1.6.0] Mock-to-Real 개발 전략 도입)
  - 4-phase development outline: Interface modeling, Manual Mocking, Real-flow transition, Production verification ([4단계 개발 아웃라인: 인터페이스 모델링, 수동 Mocking, 실제 연동, 상용 검증])
  - Manual Mocking management with failure/error injection ([수동 Mocking 관리 및 실패/에러 인젝션 지침])
  - Detailed development task rules in `ai-rules/tasks/development.md` ([ai-rules/tasks/development.md의 상세 개발 규칙])
  - Meeting: [20260117_dev_strategy_v1.6.0.md](ai-rules/meeting_minutes/20260117_dev_strategy_v1.6.0.md)
- [AI-Rules v1.5.0] Introduced Master History, DB Migration Strategy, and Doc Compliance Workflow ([AI-규칙 v1.5.0] 마스터 히스토리, DB 마이그레이션 전략, 문서 준수 워크플로우 도입)
  - Master document history for all project assets in `docs/HISTORY.md` ([모든 자산의 변경 이력을 통합하는 docs/HISTORY.md 도입])
  - Tool-neutral DB Migration principles following strict VC rules ([형상 관리 원칙을 따르는 도구 중립적 DB 마이그레이션 원칙 수립])
  - Documentation Compliance workflow for AI self-audit ([AI 자가 점검을 위한 문서 준수 워크플로우 도입])
  - Meeting: [20260117_governance_v1.5.0.md](ai-rules/meeting_minutes/20260117_governance_v1.5.0.md)
- [AI-Rules v1.4.0] Strengthened Git strategy with Doc/Code separation and no-immediate-merge policy ([AI-규칙 v1.4.0] 문서/코드 분리 및 즉시 머지 금지 정책을 통한 Git 전략 강화)
  - Strict branch naming: `docs/`, `feat/`, `fix/`, `research/` ([브랜치 네이밍 강제: docs, feat, fix, research])
  - Immediate merge prohibited; PR and explicit approval required ([즉시 머지 금지; PR 및 명시적 승인 필수])
  - Document Evolution Strategy defined as a separate backlog ticket ([문서 발전 전략을 독립된 백로그 티켓으로 정의])
  - Meeting: [20260117_git_strategy_v1.4.0.md](ai-rules/meeting_minutes/20260117_git_strategy_v1.4.0.md)
- [AI-Rules v1.3.0] Introduced Backlog, Roadmap, and RFC management strategies ([AI-규칙 v1.3.0] 백로그, 로드맵, RFC 관리 전략 도입)
  - Established `ROADMAP.md` for project milestones ([ROADMAP.md를 통한 마일스톤 관리])
  - Added Backlog management in `docs/backlog/` ([docs/backlog/을 통한 태스크 관리])
  - Introduced RFC process in `docs/rfc/` for major changes ([주요 변경 사항을 위한 RFC 프로세스 도입])
  - Meeting: [20260117_management_v1.3.0.md](ai-rules/meeting_minutes/20260117_management_v1.3.0.md)
- [AI-Rules v1.2.0] Enhanced governance with Env Var management, Container strategy, and Spec-First process ([AI-규칙 v1.2.0] 환경변수 관리, 컨테이너 전략, Spec-First 프로세스를 통한 거버넌스 고도화)
  - Mandatory `.env.example` and documentation ([.env.example 필수화 및 문서화])
  - Docker/DevContainers for project isolation ([Docker/DevContainers를 통한 프로젝트 격리])
  - Specification approval required before implementation ([구현 전 명세 승인 의무화])
  - Meeting: [20260117_governance_v1.2.0.md](ai-rules/meeting_minutes/20260117_governance_v1.2.0.md)
- [AI-Rules v1.1.0] Added Korean language requirement with dual-language CHANGELOG strategy ([AI-규칙 v1.1.0] 한글 기본 원칙 추가 및 CHANGELOG 이중 언어 전략 도입)
  - All project documents default to Korean (프로젝트 문서 한글 기본)
  - CHANGELOG: English main + Korean translation (CHANGELOG: 영어 메인 + 한글 병기)
  - Meeting: [20260117_korean_language.md](ai-rules/meeting_minutes/20260117_korean_language.md) (회의록)

## [1.0.0] - 2026-01-17
- Initial release
