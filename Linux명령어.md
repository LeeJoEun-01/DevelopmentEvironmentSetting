# Linux 명령어 

### local에서 원격으로 (Local -> Remote)
- [참고1](https://doheejin.github.io/linux/2021/03/03/linux-scp.html) [참고2](https://baekh-93.tistory.com/50)
- secureSRT에서 권한 오류가 난다면 local의 cmd에서 진행한다.
- scp [전송할 파일 경로] [유저명]@[IP주소]:받을 경로
- 원격에서는 뛰어쓰기가 인식이 안됨으로 파일 명에 뛰어쓰기가 있는 경우 `"Program Files"`문자열로 묶어서 표시해준다.
```
scp "C:\Program Files\apache-tomcat-9.0.65\webapps\sso.war" bizspring@###.##.###.###:/home/bizspring/tomcat/webapps
```
