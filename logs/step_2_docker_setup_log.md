**docker info**  
Client:  
 Version:    28.5.2  
 Context:    orbstack  
 Debug Mode: false  
 Plugins:  
  buildx: Docker Buildx (Docker Inc.)  
    Version:  v0.29.1  
    Path:     /Users/sysy22042026/.docker/cli-plugins/docker-buildx  
  compose: Docker Compose (Docker Inc.)  
    Version:  v2.40.3  
    Path:     /Users/sysy22042026/.docker/cli-plugins/docker-compose  
  
Server:  
 Containers: 0  
  Running: 0  
  Paused: 0  
  Stopped: 0  
 Images: 0  
 Server Version: 28.5.2  
 Storage Driver: overlay2  
  Backing Filesystem: btrfs  
  Supports d_type: true  
  Using metacopy: false  
  Native Overlay Diff: true  
  userxattr: false  
 Logging Driver: json-file  
 Cgroup Driver: cgroupfs  
 Cgroup Version: 2  
 Swarm: inactive  
 Runtimes: io.containerd.runc.v2 runc  
 Default Runtime: runc  
 Kernel Version: 6.17.8-orbstack-00308-g8f9c941121b1  
 Operating System: OrbStack  
 OSType: linux  
 Architecture: x86_64  
 CPUs: 6  
 Total Memory: 15.67GiB  
 Name: orbstack  
 Docker Root Dir: /var/lib/docker  
  
**ls logs/**  
ls: logs/: No such file or directory  
  
**pwd**  
/Users/sysy22042026/b_m1  
  
**cd ~/b_m1**  
**ls logs/**  
ls: logs/: No such file or directory  
  
**ls**  
log_step1.txt		practice		README.md  
mission			Project_notes		step_2_docker_setup_log  
  
**ls -la**  
total 96  
drwxr-xr-x@ 11 sysy22042026  sysy22042026   352  7 30 16:48 .  
drwxr-x---@ 29 sysy22042026  sysy22042026   928  7 30 16:49 ..  
-rw-r--r--@  1 sysy22042026  sysy22042026  6148  7 30 16:31 .DS_Store  
drwxr-xr-x  13 sysy22042026  sysy22042026   416  7 30 16:15 .git  
-rw-r--r--   1 sysy22042026  sysy22042026    32  7 30 16:19 .gitignore  
-rw-r--r--   1 sysy22042026  sysy22042026  6423  7 30 15:54 log_step1.txt  
-rw-r--r--   1 sysy22042026  sysy22042026  8459  7 30 16:36 mission  
drwxr-xr-x   3 sysy22042026  sysy22042026    96  7 30 15:46 practice  
-rw-r--r--   1 sysy22042026  sysy22042026  1038  7 30 16:20 Project_notes  
-rw-r--r--   1 sysy22042026  sysy22042026   408  7 30 16:39 README.md  
-rw-r--r--   1 sysy22042026  sysy22042026  4389  7 30 16:52 step_2_docker_setup_log  
  
**mkdir logs**  
  
**mv log_step1.txt logs/**  
**mv step_2_docker_setup_log logs/**  
  
**ls logs/**  
log_step1.txt		step_2_docker_setup_log  
  
**git add .**  
**git commit -m "docs: update readme steps and organize logs folder"**  
**git push**  
[main 759cfc0] docs: update readme steps and organize logs folder  
 8 files changed, 316 insertions(+), 7 deletions(-)  
 create mode 100644 .DS_Store  
 create mode 100644 Project_notes  
 rename log_step1.txt => logs/log_step1.txt (100%)  
 create mode 100644 logs/step_2_docker_setup_log  
 create mode 100644 mission  
 create mode 100644 practice/test.txt  
Total 11 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)  
To https://github.com/soy7yos/b_m1.git  
   5d565d9..759cfc0  main -> main  
  
**echo $SHLVL   # 셸 중첩 레벨 확인 (script 안이면 보통 2 이상)**  
zsh: number expected  
  
**ps -p $PPID   # 부모 프로세스 확인 → "script"가 보이면 로깅 중**  
ps: illegal argument: #  
usage: ps [-AaCcEefhjlMmrSTvwXx] [-O fmt | -o fmt] [-G gid[,gid...]]  
          [-g grp[,grp...]] [-u [uid,uid...]]  
          [-p pid[,pid...]] [-t tty[,tty...]] [-U user[,user...]]  
       ps [-L]  
  
**echo $SHLVL**  
4  
  
**ps -p $PPID**  
  PID TTY           TIME CMD  
14895 ttys001    0:00.01 script step_2_docker_setup_log  
  
**exit**  
