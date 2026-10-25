# GitHub Actions 기본 문법 실습

GitHub Actions의 이벤트, Job, Step, 실행 환경, 변수 참조를 익히기 위한 학습 저장소입니다.

[워크플로 코드](.github/workflows/deploy.yml) · [실행 기록](https://github.com/DFRAKE/github-actions-study/actions)

## 현재 워크플로

| 항목 | 설정 |
| :--- | :--- |
| 실행 조건 | `main` 브랜치에 push |
| 실행 환경 | `ubuntu-latest` |
| 출력 실습 | Hello World, 여러 줄 명령 |
| 기본 변수 | `GITHUB_SHA`, `GITHUB_REPOSITORY` |
| Secret 참조 | `MY_NAME`, `MY_HOBBY` |

파일명은 `deploy.yml`이지만 현재 내용은 출력과 변수 참조 실습입니다. 애플리케이션 빌드·테스트·서버 배포 단계는 없습니다.

## 확인 방법

1. [워크플로 파일](.github/workflows/deploy.yml)을 읽습니다.
2. [Actions 탭](https://github.com/DFRAKE/github-actions-study/actions)에서 기존 실행과 각 Step을 확인합니다.
3. 새 실행이 필요하면 현재 이벤트 조건에 따라 `main` push로 실행됩니다. 이 README 추가 PR 자체는 `main` push가 아니므로 이 워크플로를 실행하지 않습니다.

Secret 값은 문서·코드·로그에 직접 적지 않습니다. 현재 코드는 Secret 참조 문법을 보여줍니다. 실제 민감한 값을 사용하기 전에는 값을 출력하는 실습 구문을 정리하고, 검증에는 더미 값을 사용합니다.

## 다음 학습 과제

- 수동 실행용 `workflow_dispatch` 추가
- 최소 권한 `permissions: contents: read` 명시 검토
- 실제 앱의 checkout → build → test 단계 연결
- 실행 성공 여부를 확인한 후 워크플로 상태 배지 추가

위 항목은 후속 계획이며 현재 구현된 기능을 뜻하지 않습니다.
