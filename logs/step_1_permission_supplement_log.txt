**# script 세션 안에서 실행**
**cd ~/b_m1/practice**
**mkdir perm_test_dir**
**ls -ld perm_test_dir          # 변경 전 권한 확인**
**chmod 700 perm_test_dir**
**ls -ld perm_test_dir          # 변경 후 확인 (700 = 소유자만 rwx)**
**chmod 755 perm_test_dir       # 필요 시 복구**
**ls -ld perm_test_dir**
**exit                          # script 세션 종료**

zsh: command not found: #
ls: #: No such file or directory
ls: 권한: No such file or directory
ls: 변경: No such file or directory
ls: 전: No such file or directory
ls: 확인: No such file or directory
drwxr-xr-x  2 sysy22042026  sysy22042026  64  8  2 14:46 perm_test_dir
zsh: unknown file attribute: 7
chmod: #: No such file or directory
chmod: 필요: No such file or directory
chmod: 시: No such file or directory
chmod: 복구: No such file or directory
drwxr-xr-x  2 sysy22042026  sysy22042026  64  8  2 14:46 perm_test_dir
exit: too many arguments

--- 재실행: perm_test_dir chmod 700 확인 ---

**ls -ld perm_test_dir**
drwxr-xr-x  2 sysy22042026  sysy22042026  64  8  2 14:46 perm_test_dir

**chmod 700 perm_test_dir**

**ls -ld perm_test_dir**
drwx------  2 sysy22042026  sysy22042026  64  8  2 14:46 perm_test_dir

**chmod 755 perm_test_dir**

**ls -ld perm_test_dir**
drwxr-xr-x  2 sysy22042026  sysy22042026  64  8  2 14:46 perm_test_dir
