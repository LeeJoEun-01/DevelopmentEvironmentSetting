## 목차
[1. 인텔리제이 설치](#IntelliJ-IDEA-설치)  
[2. IntelliJ에서 java와 gradle 사용](#IntelliJ에서-java와-gradle-사용)  
[3. IntelliJ에서 한글 깨질 때](#IntelliJ에서-한글-파일-깨질-때)  
[4. Spring Boot 프로젝트 생성](#Spring-Boot-프로젝트-생성)  
[5. Error](#Error)

# IntelliJ IDEA 설치
- 'Community' 버전 (무료 버전이지만 톰캣,ioc 등등의 기능들이 없다.....!)
- 'Ultimate' 버전 (유료 버전이지만 학생 인증하면 무료!)
- Window
  - [인텔리제이 설치 시 선책 옵션](https://goddaehee.tistory.com/195)

# IntelliJ에서 java와 gradle 사용
(java와 gradle의 버전이 호환되어야 한다!)
- java version: jdk-14.0.2
- gradle version: gradle-6.4.1-bin

## java 버전 변경하는 방법
#### File -> Project Structure(ctrl+shift+alt+s) -> SDK 변경
![image](https://user-images.githubusercontent.com/78733700/175238650-41f0a983-8533-418b-88b1-a2d263f1be25.png)
## gradle 버전 변경하는 방법
#### File -> Settings(ctrl+alt+s) -> Build, Execution, Deployment -> Build Tools -> gradle 
1. gradle이 설치되어있는 위치를 지정하는 경우 
![image](https://user-images.githubusercontent.com/78733700/175237259-98966c46-90a3-4661-82f8-bedc434a0d61.png)
2. 'gradle-wrapper.properties' file 지정하는 경우 => 파일에서 gradle 버전을 수정해주고 리로드해주면 된다.


# IntelliJ에서 한글 파일 깨질 때
### 1. Error: nmappable character for encoding x-windows-949 경우
  - Settings(ctrl + alt + s) -> File Encodings
  - Encoding 방법을 다 UTF-8로 변경!!
![image](https://user-images.githubusercontent.com/78733700/177230088-399477de-ce2c-404a-bca8-aba94f82b9a8.png)

### 2. 콘솔에서 한글 깨지는 경우
  - [Help] -> [Edit Custom VM Options...]
  - 맨 아래 밑의 코드 두 줄 추가
  ```
  -Dfile.encoding=UTF-8
  -Dconsole.encoding=UTF-8
  ```
  ![image](https://user-images.githubusercontent.com/78733700/177230253-f82f4e44-ec85-4932-b3c8-8beeb9883a91.png)

  - 인텔리제이 재시작
    + 재시작을 해도 안된다면?
    + `build`파일 삭제 후 다시 run
<!-- 참고링크: https://beemiel.tistory.com/4 -->

# Spring Boot 프로젝트 생성
- [spring initializr](https://start.spring.io/)
![image](https://user-images.githubusercontent.com/78733700/182294531-3addbc3e-7a17-4ecb-b9fe-2c37dd50d43b.png)


# Error
### :boom:버전 에러
=> 발생이유! 외부에서 만들어온 spring boot project와 인텔리제이 자바 버전이 달라서 생기는 에러!  
```java
source release 11 requires target release 11
```
:point_right: 1. setting > build, Execution, Deployment > gradle projects의 using을 IntelliJ로 바꿔준다.
![image](https://user-images.githubusercontent.com/78733700/182502883-c7ad0fac-3dec-4563-bf5f-a5a1a563aec3.png)  
:point_right: 2. Project Structure에 들어가서 `project`와 `SDKs`에서 자바 버전을 spring boot와 일치해주면 해결완료!
<!-- 참고: https://oh-sh-2134.tistory.com/23  -->
