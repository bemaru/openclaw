# OpenClaw 분석

## 메타 정보

| 항목 | 내용 |
|------|------|
| 저장소 | [openclaw/openclaw](https://github.com/openclaw/openclaw) |
| 주요 언어 | TypeScript (ESM) |
| 라이선스 | MIT — 완전 자유 사용, 수정, 재배포 가능 |
| Stars | 186K+ |
| 분석일 | 2026-02-12 |
| 성격 | 자가호스팅 멀티채널 AI 어시스턴트 게이트웨이 |

## 핵심 인사이트

1. **Channel Adapter 패턴으로 극단적 확장성 달성** — 공유 라우팅/청킹/보안 로직과 채널별 프로토콜 처리를 타입 기반 Adapter로 깔끔하게 분리. 새 채널 추가 시 Adapter 구현만 하면 되는 구조
2. **단일 Gateway = Single Source of Truth** — 모든 채널, 세션, 에이전트 라우팅이 중앙 Gateway에서 관리되어 메시지 순서 보장과 설정 일관성 유지
3. **계층적 바인딩 라우팅** — peer → guild → team → account → channel → default 순으로 fallback하는 다단계 라우팅으로, 사용자별/그룹별/채널별 에이전트 분기를 설정만으로 해결
4. **로컬 우선 + 파일시스템 기반 상태 관리** — 세션, 설정, 스킬 모두 `~/.openclaw/`에 저장. 클라우드 의존성 제거로 프라이버시 보장과 백업/이동 용이성 확보
5. **정교한 스트리밍 State Machine** — Thinking 블록 감지, 마크다운 코드 스팬 인식, 중복 메시지 정규화 등을 통한 LLM 스트리밍 응답의 안정적 처리

## 문서 구성

| 문서 | 내용 |
|------|------|
| [overview.md](./overview.md) | 프로젝트 철학, 차별점, 기술 스택 선택 이유 |
| [core-logic.md](./core-logic.md) | 실행 흐름, 핵심 알고리즘/패턴 상세 분석 |
| [architecture.md](./architecture.md) | 모듈 구조, 의존 관계, 설계 패턴 |
