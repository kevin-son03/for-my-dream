<pre><code>#Pwnable.kr - fd

ssh fd@pwnable.kr -p2222

ls -l

cat fd.c

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

char buf[32];

int main(int argc, char* argv[], char* envp[]){
    if(argc<2){
        printf("pass argv[1] a number\n");
        return 0;
    }
    int fd = atoi(argv[1]) - 0x1234; // 여기서 fd 값이 결정됨!
    int len = read(fd, buf, 32);     // fd로부터 데이터를 읽어옴
    if(!strcmp("LETMEWIN\n", buf)){
        printf("good job :)\n");
        system("/bin/cat flag");     // 우리가 원하는 플래그 출력!
        exit(0);
    }
    printf("learn about Linux file descriptor\n");
    return 0;
}

*핵심코드
int fd = atoi(argv[1]) - 0x1234;
len = read(fd, buf, 32);


0X1234 의 10진수를 인자로 넣어서 실행하기
./fd 4660

LETMEWIN
을 입력하여 flag를 cat을 얻는다

int fd = atoi(argv[1]) - 0x1234; 이부분을 보면 fd 값이 0이 되어야 함
리눅스에서 FD 0 = 표준입력(키보드)을 의미하기때문에 우리가 친 글자를 프로그램이
읽을 수 있게됨

그럼 flag값이 출력 됌

우리가 방금 한 일
1.계산: 0x1234가 10진수로 4660이라는 걸 알아냈어.

2.조작: 인자값으로 4660을 넘겨서 프로그램 내부의 fd 변수를 0으로 만들었지.

3.입력: fd가 0이 되니까 프로그램이 '파일' 대신 **'키보드(표준 입력)'**로부터 데이터를 기다리게 됐고, 그때 우리가 LETMEWIN을 쏴준 거야.

