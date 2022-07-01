# DevelopmentEvironmentSetting
환경 설정


# Apache 2.4 + PHP 7.4.30 
## 1. Apache 2.4 설치  
  - [Apache 2.4 다운로드](https://www.apachelounge.com/download/)
  - Apache 2.4 파일을 원하는 경로에 압축 해제
  - `\conf`의 `httpd.conf` 파일 수정

  ```
  ...
  
  <!-- (예시)Define SRVROOT "C:/Program Files/httpd-2.4.54-win64-VS16/Apache24" -->
  Define SRVROOT "아파치 경로"
  ServerRoot "${SRVROOT}"
  
  ...
  
  # 포트
  Listen 80
 
  ...
  
  # ServerName 변경
  <!-- ServerName localhost:80 -->
  ServerName localhost:포트
  ```
  - cmd에서 `apache24\bin` 폴더로 이동해서 아래 명령어로 설치를 한다.
  ```
  // 아팟치 설치
  httpd.exe -k install
  // 아팟치 시작
  httpd -k start
  ```
  - 오류나는 경우 아파치 재설치 후 시작하기.
  ```
  httpd.exe -k uninstall
  ```
  
## 2. PHP 7.4.30 설치 
  - [PHP 7.4.4 다운로드](https://windows.php.net/download/)
    + Binaries and sources Releases에서 원하는 버전, 비트, Thread Safe 후 Zip 파일 다운로드
      - ('php7apache2_4.dll' 파일이 있어야 함으로 무조건 **Thread Safe**로 다운로드!!)
      - ### [세팅 시작]
      1) php.ini-production 파일을 복사해서 `php.ini`으로 이름 변경
      2) php.ini 파일을 열어서 extension_dir 찾아서 ext 풀더의 경로를 입력한다. (메모장에서 관리자 권한으로 열어서 편집)
      ```
      ; Directory in which the loadable extensions (modules) reside.
      ; http://php.net/extension-dir
      ;extension_dir = "./"
      ; On windows:
      // 변경 전
      // ;extension_dir = "ext"
      // 변경 후 
      extension_dir = "C:\Program Files\php-7.4\ext"
      ```
      3) apache24\conf\httpd.conf 파일을 열어서 밑의 과정대로 코드를 수정한다. (메모장에서 관리자 권한으로 열어서 편집)
      4) DirectoryIndex 를 찾아서 index.php를 추가한다.
      ```
      < IfModule dir_module>
          DirectoryIndex index.php index.html
      </IfModule>
      ```
      5) 맨아래 부분에 밑의 코드를 추가합니다.
      ```
      PHPIniDir "C:/php7" //php.ini 파일의 경로
      LoadModule php7_module "C:/php7/php7apache2_4.dll"  // php7apache2_4.dll 파일의 경로
      AddType application/x-httpd-php .html .php
      AddHandler application/x-httpd-php .php
      ```
      6) 아파치를 다시 시작 후 "http://localhost:80" It works!라고 뜨면 성공!! 
      ```
      $ httpd -k restart
      ```
