### Install
* 스크립트로 설치하는 것이 편하다.
```
curl -fsSL https://get.docker.com/ | sudo sh
```
* 사용자 권한 주기 . 기본적으로 root 권한이 필요하므로 현 사용자를 docker 그룹에 넣는것이 편함. 
```
# 사용자에게 권한주기
sudo usermod -aG docker seunghoryu
```
### Run
* 터미널에서 docker version 커맨드 날렸을때 다음처럼 clien/server가 같이 나오면 정상 
```
Client:
 Version:   17.12.0-ce
 API version:   1.35
 Go version:    go1.9.2
 Git commit:    c97c6d6
 Built: Wed Dec 27 20:10:36 2017
 OS/Arch:   linux/amd64
Server:
 Engine:
  Version:  17.12.0-ce
  API version:  1.35 (minimum version 1.12)
  Go version:   go1.9.2
  Git commit:   c97c6d6
  Built:    Wed Dec 27 20:09:12 2017
  OS/Arch:  linux/amd64
  Experimental: false
```
* 만약 server 부분이 권한문제로 안나온다면 sudo 붙이면 나올것임..  (위에말한것처럼 재부팅 or 로그아웃 해야 sudo 없이 가능.)
### Command
* 이미지 검색 
  * docker search ubuntu
    * --limit	(25)	Max number of search results
    * --no-trunc		Don’t truncate output
    * --stars , -s		Only displays with at least x stars (deprecated)
* 이미지 다운
  * docker pull ubuntu:latest
* 이미지 list
  * docker images
* 이미지 삭제
  * docker rmi ubuntu:latest
  * docker rmi fd484f19954f  <-- IMAGE ID
* Container 실행
  * run = create + start 임
  * docker run [OPTION] IMAGE[:TAG|@DIGEST] [COMMAND]
    * -name: name을 지정하면 다루기편함. (시작, 중지 같은거할때 사용할수있음)
    * -it: -i -t 동시에 사용한 것 터미널 입력을 위한 옵션
    * -rm: process 종료시 컨테이너 자동 삭제
    * -d: 백그라운드 모드    
    * -link: 컨테이너 연결
    * -e: 환경변수가있는 경우 환경변수추가 (비밀번호 전달시 자주사용)
      * -e MYSQL_ROOT_PASSWORD=examplepassword
    * -v: 호스트 PC와 컨테이너 디렉토리 연결 (mount)
    * -p: 호스트 PC와 컨테이너 포트 연결 (port forwarding)
  * Example
    * docker run --rm -it my-ubuntu /bin/bash
    * docker run -d -p 3306:3306
    * docker run -d -p 6379:6379 redis
    * docker run -it --rm ubuntu:14.04 bash
    * docker run -it -e HELLO_VAR="Hello World" ubuntu:14.04 bash
* Container list
  * docker ps [OPTION]
    * -a: all
* 실행중인 Container에 접속
  * docker attatch ubuntu
* Container start/restart/stop
  * docker [start/restart/stop] d32ca75ac35d
* exec를 사용해서 컨테이너 안의 명령실행하기
  * docker exec my-ubuntu apt-get update
  * docker exec my-ubuntu apt-get install -y redis-server
* 컨테이너 삭제
  * docker rm my-ubuntu
  
  
  
