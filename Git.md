# Github 관련 명령어

<!-- 목차 -->
<!-- [* gitignore 적용 안될 때](#gitignore-적용-안될-때) -->

### git 기본 명령어 
<a href="https://ninth-sleep-ef8.notion.site/Git-cd1b38848cf448b484d2e43431f676ff">
<img src="https://img.shields.io/badge/Notion-ffffff?style=flat-square&logo=notion&logoColor=000000"/></a>

### gitignore 적용 안될 때 
- 상황 1. 이미 모든 파일을 git이 추적 중인 겨우
- 상황 2. 이미 추적 중인 파일 몇 개만 무시하고 싶은 경우
  - 1. `.gitignore` 파일을 제대로 작성했는지 확인
  - 2. 현재 상태에서 무시하고자 하는 파일을 제외하고 다 commit을 해준다. (:warning: 안 해주면 다 날라감으로 주의하자)
  - 3. 루트 폴더(최상위 폴더)에 간 후 git rm -r --cached 파일명1 파일명2 ...
    ```
    git rm -r --cached 파일명1 파일명2
    ```
  - 4. 이제부터는 선택한 파일의 gin index가 다 초기화 되었음으로 .gitignore가 다시 적용된다.
  - 5. 따라서 평상시대로 `git add .`해주고 `git commit -m "gitignore 다시 적용"`
- 상황 3. 반대로 .gitignore에 있었던 파일을 다시 추적하고 싶을 경우

<!--gitignore 참고: https://coding-groot.tistory.com/59 -->
<!--마크다운 이모지 이름: https://inpa.tistory.com/entry/MarkDown-%F0%9F%93%9A-Emoji-%EC%9D%B4%EB%AA%A8%ED%8B%B0%EC%BD%98-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0  -->
