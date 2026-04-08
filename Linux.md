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




