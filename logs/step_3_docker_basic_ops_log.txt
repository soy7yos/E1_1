**docker run hello-world**
Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

**docker images**
REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
hello-world   latest    e2ac70e7319a   4 months ago   10.1kB

**docker run -it --name my_ubuntu ubuntu bash**
Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
Digest: sha256:3131b4cc82a783df6c9df078f86e01819a13594b865c2cad47bd1bca2b7063bb
Status: Downloaded newer image for ubuntu:latest

root@4f2449ded5e9:/# **ls**
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

root@4f2449ded5e9:/# **echo hello**
hello

root@4f2449ded5e9:/# **exit**
exit

**docker ps**
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

**docker ps -a**
CONTAINER ID   IMAGE         COMMAND    CREATED              STATUS                      PORTS     NAMES
4f2449ded5e9   ubuntu        "bash"     About a minute ago   Exited (0) 44 seconds ago             my_ubuntu
4056bd0fe0e4   hello-world   "/hello"   2 minutes ago        Exited (0) 2 minutes ago              suspicious_fermat
926a5bd316c3   hello-world   "/hello"   3 minutes ago        Exited (0) 3 minutes ago              elastic_brattain

**docker run -d --name my_nginx -p 8080:80 nginx**
Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
Digest: sha256:5a88c9c45479443d7be2eadc894b4ed0a9801bae03d97a5760ae13b5c2005942
Status: Downloaded newer image for nginx:latest
8f897f64208920505de1a1dc001b02bb7bf01285aa5fe235fe7c95ef6539faf9

**docker logs my_nginx**
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2026/07/30 08:23:34 [notice] 1#1: using the "epoll" event method
2026/07/30 08:23:34 [notice] 1#1: nginx/1.31.3
2026/07/30 08:23:34 [notice] 1#1: built by gcc 14.2.0 (Debian 14.2.0-19)
2026/07/30 08:23:34 [notice] 1#1: OS: Linux 6.17.8-orbstack-00308-g8f9c941121b1
2026/07/30 08:23:34 [notice] 1#1: start worker processes
2026/07/30 08:23:34 [notice] 1#1: start worker process 29
2026/07/30 08:23:34 [notice] 1#1: start worker process 30
2026/07/30 08:23:34 [notice] 1#1: start worker process 31
2026/07/30 08:23:34 [notice] 1#1: start worker process 32
2026/07/30 08:23:34 [notice] 1#1: start worker process 33
2026/07/30 08:23:34 [notice] 1#1: start worker process 34

**docker stats --no-stream**
CONTAINER ID   NAME       CPU %     MEM USAGE / LIMIT     MEM %     NET I/O         BLOCK I/O       PIDS
8f897f642089   my_nginx   0.00%     6.387MiB / 15.67GiB   0.04%     1.13kB / 126B   4.1kB / 4.1kB   7

**docker stop my_nginx**
my_nginx

**docker rm my_nginx my_ubuntu**
my_nginx
my_ubuntu

**docker ps -a**
CONTAINER ID   IMAGE         COMMAND    CREATED          STATUS                      PORTS     NAMES
4056bd0fe0e4   hello-world   "/hello"   9 minutes ago    Exited (0) 9 minutes ago              suspicious_fermat
926a5bd316c3   hello-world   "/hello"   10 minutes ago   Exited (0) 10 minutes ago             elastic_brattain

**docker run -dit --name test_ubuntu ubuntu bash**
be5d4fb9aef7361ca2fbd1a193481821ef2cfdd5b1e846d3fa3fe6d7d1fdb991

**docker exec -it test_ubuntu bash**
root@be5d4fb9aef7:/# **exit**
exit

**docker ps**
CONTAINER ID   IMAGE     COMMAND   CREATED         STATUS         PORTS     NAMES
be5d4fb9aef7   ubuntu    "bash"    6 minutes ago   Up 6 minutes             test_ubuntu

**docker attach test_ubuntu**
root@be5d4fb9aef7:/# **exit**
exit

**docker ps**
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

**exit**
