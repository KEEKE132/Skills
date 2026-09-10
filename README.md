# Skills

개인 Codex 스킬의 원본 저장소입니다. 각 최상위 디렉터리는 독립적인 Codex 스킬이며, `SKILL.md`의 메타데이터를 기준으로 자동 적용됩니다.

## 사용 방법

이 레포를 복제한 뒤 필요한 스킬 디렉터리를 Codex의 사용자 스킬 경로(`C:\\Users\\dksvl\\.codex\\skills`)에 복사하거나, Codex의 GitHub 스킬 설치 흐름에서 이 레포와 해당 디렉터리를 선택하세요. 기존의 평면 스킬 구조를 유지해 필요한 스킬만 독립적으로 설치·갱신할 수 있습니다.

## 포함 스킬

### 개발 워크플로우 — Superpowers

`obra/superpowers` 전체 스킬팩입니다. 구현 전 설계, 디버깅, 테스트 주도 개발, 병렬 작업, 코드 리뷰, 완료 검증을 연결합니다.

- `brainstorming` — 구현 전 요구와 설계를 구체화합니다.
- `dispatching-parallel-agents` — 독립적인 작업을 병렬 에이전트에게 분배합니다.
- `executing-plans` — 승인된 구현 계획을 단계적으로 실행합니다.
- `finishing-a-development-branch` — 구현 완료 후 브랜치 마무리 절차를 안내합니다.
- `receiving-code-review` — 받은 코드 리뷰를 검토하고 대응합니다.
- `requesting-code-review` — 변경사항의 코드 리뷰를 요청·준비합니다.
- `subagent-driven-development` — 하위 에이전트 중심의 개발 흐름을 운영합니다.
- `systematic-debugging` — 증거 기반으로 버그를 재현·분석·수정합니다.
- `test-driven-development` — 테스트를 먼저 작성하는 개발 흐름을 적용합니다.
- `using-git-worktrees` — 격리된 Git worktree에서 안전하게 작업합니다.
- `using-superpowers` — 현재 작업에 맞는 Superpowers 스킬을 먼저 선택합니다.
- `verification-before-completion` — 완료 주장 전에 검증 증거를 확인합니다.
- `writing-plans` — 구현 계획을 작성합니다.
- `writing-skills` — 새 스킬을 설계·검증합니다.

### 설계·조사

- `grill-with-docs` — 설계/계획을 집중적으로 질문하며 ADR과 용어 문서를 만듭니다.
- `domain-modeling` — 용어집(`CONTEXT.md`)과 ADR로 도메인 모델을 정리합니다.
- `research` — 1차 출처를 조사해 결과를 레포의 Markdown 문서로 남깁니다.
- `to-spec` — 현재 대화와 코드베이스를 구현 명세 및 이슈로 종합합니다.

### 검증·보안

- `playwright` — 실제 브라우저를 자동화해 UI 흐름을 확인하고 디버깅합니다.
- `security-threat-model` — 코드 근거로 자산, 신뢰 경계, 공격 경로, 완화책을 담은 위협 모델을 작성합니다.

### GitHub

- `gh-address-comments` — 현재 브랜치의 열려 있는 PR 리뷰/이슈 코멘트를 수집하고 선택한 항목을 처리합니다.
- `gh-fix-ci` — GitHub Actions PR 체크 실패를 조사하고, 승인 후 수정합니다.

`pr-review-response`는 `gh-address-comments`와 역할이 겹쳐 제거했습니다. 일반적인 PR 분석에는 기존 `pr-review`를 계속 사용합니다.

## 호출 정책

토큰 사용량을 제한하기 위해 개발 툴킷은 **핵심 상황별 스킬만 자동 호출**하고, 설계·오케스트레이션·광범위한 조사처럼 비용이 커질 수 있는 흐름은 명시 호출로 전환했습니다. 명시 호출 대상에는 SKILL.md frontmatter의 `disable-model-invocation: true`와 Codex 인터페이스 정책 `agents/openai.yaml`의 `allow_implicit_invocation: false`를 함께 사용합니다.

### 자동 호출

- `systematic-debugging` — 버그, 테스트 실패, 예기치 않은 동작의 원인 분석.
- `verification-before-completion` — 완료·수정·통과를 주장하기 전의 검증.
- `playwright` — 실제 브라우저 자동화가 필요한 UI 흐름 점검.
- `gh-fix-ci` — GitHub Actions PR 체크 실패의 조사와 수정 계획.
- `gh-address-comments` — 현재 PR의 리뷰·이슈 코멘트 대응.
- `domain-modeling` — 용어, `CONTEXT.md`, ADR을 실제로 만들거나 갱신하는 작업.

### 명시 호출

- `grill-with-docs`, `research`, `to-spec`, `security-threat-model`
- `using-superpowers` 및 나머지 Superpowers 워크플로우: `brainstorming`, `dispatching-parallel-agents`, `executing-plans`, `finishing-a-development-branch`, `receiving-code-review`, `requesting-code-review`, `subagent-driven-development`, `test-driven-development`, `using-git-worktrees`, `writing-plans`, `writing-skills`

예: `/research`, `/security-threat-model`, `/using-superpowers`. 특히 `using-superpowers`는 더 이상 모든 대화의 글로벌 진입점으로 자동 동작하지 않으며, 사용자가 전체 워크플로우를 요청할 때만 실행됩니다.

## 원본과 라이선스

벤더링한 스킬은 아래 원본 커밋을 기준으로 합니다. 호출 정책을 위한 SKILL.md frontmatter 외에는 원문 파일과 포함된 라이선스/NOTICE를 수정하지 않았습니다.

| 구성 | 원본 | 고정 커밋 | 라이선스·고지 |
| --- | --- | --- | --- |
| Superpowers 전체 스킬팩 | [obra/superpowers](https://github.com/obra/superpowers) | `b36e0829c6d0140e93cfef2ca599b1b07d4a7797` | MIT — [LICENSES/obra-superpowers-MIT.txt](LICENSES/obra-superpowers-MIT.txt) |
| grill-with-docs, domain-modeling, research, to-spec | [mattpocock/skills](https://github.com/mattpocock/skills) | `3cca18b368ae95cdbdebbff572ccafa662551015` | MIT — [LICENSES/mattpocock-skills-MIT.txt](LICENSES/mattpocock-skills-MIT.txt) |
| playwright, gh-fix-ci, gh-address-comments, security-threat-model | [openai/skills](https://github.com/openai/skills) | `49f948faa9258a0c61caceaf225e179651397431` | Apache-2.0 — 각 스킬의 `LICENSE.txt`; Playwright의 `NOTICE.txt` 포함 |

재배포 시 위 MIT 라이선스와 각 OpenAI 스킬의 Apache-2.0 `LICENSE.txt` 및 해당 `NOTICE.txt`를 함께 유지해야 합니다.
