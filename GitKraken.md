GitKraken 
### branch 생성
-> 상단의 메뉴바에서 `branch 버튼`을 눌러 LOCAL에 branch를 하나 생성해주고 PUSH 하여 REMOTE에도 branch를 생성해준다.

### pull(rebase)
#### rebase란? 
: 커밋의 base를 다시(re) 정하는 작업 -> master와 dev 브랜치의 공통 조상 커밋부터 dev 브랜치까지의 모든 커밋의 base를 master 브랜치의 위치로 바꾸어라. 
1. 사진처럼 REMOTE에서 기준이 되는 브랜치에 마우스를 가지고가서 우클릭
2. ![스크린샷 2022-11-01 오후 9 26 28](https://user-images.githubusercontent.com/78733700/199232018-e799f752-97f4-4452-813f-328ce12114e9.png). 
3. 그 중에 `rebase --- onto ---- ` 를 누르면 rebase 성공!

#### 에러가 발생했다면??? 🧨
