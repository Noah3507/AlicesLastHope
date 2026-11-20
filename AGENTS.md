# AlicesLastHope 작업 규칙

이 규칙은 저장소 전체의 후속 Codex 작업에 적용한다.

- 파일을 수정하기 전에 `git status --short --branch`와 `git branch --show-current`로 작업 트리와 현재 브랜치를 확인한다. 기존 변경을 보존하고 작업 범위 밖의 파일을 수정하지 않는다.
- `main`에서 기능을 개발하지 않는다. 요청된 기능은 별도 작업 브랜치에서 진행한다.
- Unity 에셋을 이동하거나 이름을 변경할 때 해당 `.meta`를 함께 옮기고 GUID를 보존한다. 신규 에셋과 폴더의 `.meta`는 같은 변경에 포함한다.
- 씬이나 프리팹을 수정하기 전에 협업 문서와 실제 담당 현황을 확인한다. 동시에 같은 파일을 수정하지 않도록 담당자와 조율한다. YAML 충돌이 생기면 의도한 변경을 확인하고 Unity에서 씬과 참조를 검증한다.
- `Packages/` 또는 `ProjectSettings/`를 변경하기 전에 사용자 승인을 받는다. Unity가 관련 파일을 자동 갱신할 수 있는 작업에도 이 규칙을 적용한다.
- `git reset --hard`, `git clean -fdx`, 작업을 덮어쓰는 `git checkout` 또는 `git restore`, 강제 push, 공유 히스토리 재작성 등 파괴적 Git 명령을 실행하지 않는다.
- 완료 보고에 변경 파일 또는 경로, 검증과 테스트 결과, 실행하지 못한 검사와 그 이유를 포함한다.

## 커밋 메시지

- 모든 커밋 메시지는 영어로 작성한다. 제목은 Conventional Commits 형식인 `type: concise description`을 사용한다.
- 기본 유형은 `feat`, `fix`, `refactor`, `docs`, `chore`, `test`, `perf`, `build`, `ci`다. 팀 전용 유형으로 `art`, `anim`, `level`도 허용한다.
- 제목에 변경 대상과 내용을 구체적으로 적고, 관련 변경만 하나의 커밋으로 묶는다. 예시 `docs: define team commit message rules`

## 기능 개발과 기획 결정

- 기능 작업 전 관련 기획 문서와 [결정 기록](Docs/DESIGN_DECISIONS.md), [미확정 질문](Docs/OPEN_QUESTIONS.md)을 확인한다.
- 구현에 영향을 주는 미확정 사항은 질문 ID와 함께 사용자에게 묻는다. 선택지와 추천안 및 이유를 제시하고, 구현을 막는 결정은 승인까지 기다린다. 승인 없이 게임 디자인을 확정하지 않는다.
- 비차단 사항은 교체할 수 있는 임시 가정으로 격리한다. 질문 ID, 적용 범위, 임시 값 또는 동작, 제거 조건을 기록하고 확정 기획으로 취급하지 않는다.
- 사용자가 승인한 결정은 결정 기록에 근거와 함께 반영하고 해당 질문의 상태를 갱신한다. 기능 작업 후 새로 발견한 기획 질문도 미확정 질문 문서에 기록한다.

[팀 협업 가이드](Docs/TEAM_COLLABORATION.md)
