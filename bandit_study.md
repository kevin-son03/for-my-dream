bandit 

level 0. 
ssh bandit0@bandit.labs.overthewire.org -p (port)

level 1.
ls, cat

level 2.
ls, cat./

level 3.
ls -al, cat ./"--"

level 4.
ls -al, cd, cat

level 5.
ls -al, cd, file ./*

level 6.
ls -al, cd, find ./ -type f -size 1033c ! -executable

level 7.
ls, find / -user bandit7 -group bandit6 -size33c 2> /dev/null

level 8.
ls -al, grep

level 9.
ls, sort, unip -u


level 10.
strings, grep

level 11.
base64 -d

level 12.
ROT13

level 13.
xxd -r, mv, gunzip, bzip2 -d, tar -xf

