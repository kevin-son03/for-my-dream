##Linux

<pre><code>'''

id 
-유저 id, 그룹 id

pwd
-print Working Directory (현재 경로 출력)

ls
-List

ls -l
-상세정보도 보여줌

ls -l /
임의 내용도 출력해줌

/
-절대 경로

..
-상대 경로 (부모 디렉터리로 이동)

cd
-Change Directory

mkdir
-Make Directory

touch
-위 mkdir new_file 로 만든 디렉토리에 새로운 파일 만드는데 사용

mv
-Move (파일 이름 변경) ex)mv new_file old_file
-위치 변경도 가능

rm
-Remove 삭제 명령어
-디렉토리 삭제는 rm -r

cat
-파일 내용 출력

file 
-파일 유형 출

echo
-입력한 텍스트 출력
-echo  "Hello world" > hello	이렇게 hello파일을 만들고 Hello world출력 가능

cp
-Copy
-디렉토리 복사는 cp-r

grep
-grep 문자열 파일 형식으로 사용 (특정 문자열 찾을 때 사용)

man
-Manual 명령어 메뉴얼 보여줌

curl
-client URL 
-curl "post주소" -d "'cat /etc/passwd'" (이렇게 서버에 명령어로  키 값 전송)
-기타 기능 많은 나중에 더 공부 필요

(wildcards)
-? 임의의 1개문자로 대체
-*임의의 0개 이상 문자로 대체

(redirection)
명령어 > 파일 =명령어 출력을 파일로 변경(덮어씀)
명령어 >> 파일 = ''(이어씀)
명령어 < 파일 =명령어 입력을 파일로 변경

| (pipe)
-출력을 다른 명령어의 입력으로 보냄


### 권한

-r :read 
-w :write
-x :execute
(2진수나 10진구로도 표현 가능)
ex) drwxrwxr-x 2 user user 
=   d 권한 	소유자 그룹
#drwxrwxr-x = d는 디렉토리, -는 일반 파일, L은 링크파일
#rwx = 소유자의 권한
#다음 rwx = 소유그룹 유저들 권한
#r-x = 나머지 유저들 권한
#user = 소유자
#다음 user 소유그룹

### 권한 명령어
#chmod : 권한을 변경하는 명령어 
rwx = 7
rw- = 6
r-- = 4
ex) chmod 764 파일명

#소유 그룹 권한 변경
변경 = chmod g+x 파일명
제거 = chmod g-wx 파일명

##chown : 파일 소유자/소유 그룹 변경 명령어 (root유저만 실행가능)
-sudo chown root hello 실행하면 user가 root로 소유자가 변경 됌

#특수 권한
-s = setuid
: 일반 사용자가 root 권한으로 실행하고 비번 변경할 수 있음.
(실행 권한에 x 대신 s 로 나타나짐) ex) rws
chmod u+s 파일명
-setgid는 그룹
chmod g+s 파일명

-t = sticky bit
: 디렉토리 소유자와 root 사용자 외에 일반 사용자가 파일 삭제 불가능
(x 대신 t 로 나타나짐) 
chmod o+t 파일명

##setuid, setgid, stixky bit
   4	    2         1

##디렉토리 구조

#/ : 절대 경로
-/bin 기본적인 명령어, 프로그램 담고 있는 디렉토리
-/boot 부팅에 필요한 파일담는 디렉토리
-/dev 하드웨어들을 파일 형태로 모아둔 d
-/etc 운영체제나 운영체제 서비스의 설정 파일을 담는 d
-/home 일반 유저의 홈 d
-/lib 시스템에 필요한 라이브러리 파일을 담는 d
-/opt 소프트웨어 패키지들은 담는 d
-/proc 리눅스 커널자원에 접근할 수 있는 파일과 프로세스 파일을 담음
-/root root 유저의 홈 디렉토리
-/sbin 기본적인 유저 명령어나 프로그램을 가지고 있는 d 
-/tmp 임시 파일 d
-/usr 사용자 바이너리, 문서, 라이브러리, 헤더파일 담는 d
-/var 실시간으로 가변적인 파일을 써야할 때 활용하는 d






