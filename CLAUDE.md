# CLAUDE.md

이 파일은 이 저장소에서 작업할 때 Claude Code(claude.ai/code)에게 제공하는 가이드입니다.

## 프로젝트 현황

TaskFlow는 TDD 기반의 할 일(to-do) 관리 앱입니다. 현재 저장소에는 의도된
최상위 구조만 존재하며, 소스 코드, 패키지 매니페스트, 설정 파일은 아직
추가되지 않았습니다:

```
backend/tests/
frontend/tests/
e2e/
```

README, 빌드 도구, 의존성 매니페스트(예: `package.json`, `requirements.txt`)도
아직 없으므로, 현재로서는 문서화할 빌드/린트/테스트 명령이 없습니다.

## 의도된 아키텍처

- `backend/` — 서버 측 애플리케이션 코드, 테스트는 `backend/tests/`에 위치.
- `frontend/` — 클라이언트 측 애플리케이션 코드, 테스트는 `frontend/tests/`에 위치.
- `e2e/` — 전체 스택을 아우르는 end-to-end 테스트.

`backend/`와 `frontend/` 각각에 전용 `tests/` 디렉터리가 있고, 최상위에
`e2e/` 디렉터리가 있다는 점은 이 프로젝트가 테스트 주도 개발(TDD) 워크플로우를
따르도록 의도되었음을 보여줍니다: 백엔드와 프론트엔드 코드 모두 먼저 실패하는
테스트를 작성한 뒤 이를 통과시키는 구현을 작성하며, `e2e/`는 스택 전체를
아우르는 플로우를 다룹니다.

## 계획된 기술 스택

아직 코드는 작성되지 않았지만, 다음 스택이 계획되어 있습니다:

- **백엔드** (`backend/`): 웹 프레임워크로 [Hono](https://hono.dev/), 데이터
  액세스를 위한 [Drizzle ORM](https://orm.drizzle.team/) + SQLite, 스키마
  검증을 위한 [Zod](https://zod.dev/).
- **프론트엔드** (`frontend/`): React, Vite로 빌드, Tailwind CSS로 스타일링.
- **테스팅**: 백엔드/프론트엔드 단위 테스트(`backend/tests/`,
  `frontend/tests/`)는 [Vitest](https://vitest.dev/), end-to-end 테스트
  (`e2e/`)는 [Playwright](https://playwright.dev/).

## 이 파일을 최신 상태로 유지하기

이 파일은 플레이스홀더입니다. 실제 코드, 프레임워크, 도구가 추가되는 즉시(예:
백엔드 프레임워크, 프론트엔드 프레임워크, 테스트 러너, 린터) 다음 내용으로
이 CLAUDE.md를 갱신하세요:

- 실제 빌드/린트/테스트 명령 (단일 테스트 실행 방법 포함).
- 여러 파일/모듈에 걸치게 되었을 때의 실제 상위 수준 아키텍처.
