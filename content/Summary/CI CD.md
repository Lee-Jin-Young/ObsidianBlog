---
tags:
  - etc
---
### CI (Continuous Integration)

- 지속적 통합
- 여러 개발자가 하나의 프로젝트를 같이 개발할 때 발생하는 불일치를 최소화 해주는 개념
- 애플리케이션 변경 사항 반영 시 자동으로 빌드 및 테스트 되어 잘못된 코드가 공유되는 것을 방지

### CD (continuous Deployment)

- 지속적 배포
- 프로젝트의 변경 사항을 가상 환경에 자동으로 배포
- 변경 사항을 배포할 때 사용하는 파이프 라인을 공유하여 번거로움을 없앨 수 있다.

### Github Actions

- Github에서 제공하는 CI / CD 툴로써 build, test, deploy등 필요한 Workflow를 등록 후 Github 내에서 특정 이벤트가 발생한 시점에서 해당 Workflow를 수행한다.
- 예) Pull Request를 올리면 자동으로 해당 코드의 테스트를 수행, master branch에 코드를 push하면 자동으로 코드 배포
- Github Repository내부에서 바로 사용 할 수 있다는 장점이 있다.

[GitHub Actions 이해 - GitHub Docs](https://docs.github.com/ko/actions/learn-github-actions/understanding-github-actions)

[Github Actions CI: 자동 빌드 및 테스트 하기](https://bcp0109.tistory.com/362)