**pwd**  
/Users/sysy22042026/b_m1  
  
**ls**  
log_1단계.txt	README.md  
  
**ls -al**  
total 16  
drwxr-xr-x   5 sysy22042026  sysy22042026  160  7 30 15:37 .  
drwxr-x---+ 21 sysy22042026  sysy22042026  672  7 30 15:37 ..  
drwxr-xr-x  13 sysy22042026  sysy22042026  416  7 30 15:32 .git  
-rw-r--r--   1 sysy22042026  sysy22042026  257  7 30 15:38 log_1단계.txt  
-rw-r--r--   1 sysy22042026  sysy22042026  444  7 30 15:22 README.md  
  
**cd ~/b_m1**  
  
**cd ..**  
  
**mmdir practice**  
zsh: command not found: mmdir  
  
**mkdir practice**  
  
**cd ~/b_m1**  
  
**mkdir practice**  
  
**cd practice**  
  
**touch test.txt**  
  
**echo "hello" > test.txt**  
  
**cat test.txt**  
hello  
  
**cp test.txt copy.txt**  
  
**mv copy.txt renamed.txt**  
  
**rm renamed.txt**  
  
**ls -l test.txt**  
-rw-r--r--  1 sysy22042026  sysy22042026  6  7 30 15:44 test.txt  
  
**chmod 000 test.txt**  
  
**cat test.txt**  
cat: test.txt: Permission denied  
  
**chmod 644 test.txt**  
  
**cat test.txt**  
hello  
  
**exit**  
