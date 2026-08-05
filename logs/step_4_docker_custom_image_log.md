**mkdir app**
**cd app**

**echo "<h1>Hello Im soy</h1>" > index.html**
**cat index.html**
<h1>Hello Im soyyyyyyyy</h1>

**cat << 'EOF' > Dockerfile**
FROM nginx:alpine
LABEL org.opencontainers.image.title="my-custom-nginx"
ENV APP_ENV=dev
COPY index.html /usr/share/nginx/html/index.html
EOF

**cat Dockerfile**
FROM nginx:alpine
LABEL org.opencontainers.image.title="myweb"
ENV APP_ENV=dev
COPY index.html /usr/share/nginx/html/index.html

**docker build -t my_web:1.0 .**
ERROR: Cannot connect to the Docker daemon at unix:///Users/sysy22042026/.orbstack/run/docker.sock. Is the docker daemon running?

**docker info**
Client:
 Version:    28.5.2
 Context:    orbstack
Server:
 Containers: 3
  Running: 0
  Stopped: 3
 Images: 3
 Server Version: 28.5.2
 Operating System: OrbStack
 OSType: linux
 Architecture: x86_64

**docker build -t my_web:1.0 .**
[+] Building 6.6s (7/7) FINISHED
 => [internal] load build definition from Dockerfile
 => [internal] load metadata for docker.io/library/nginx:alpine
 => [internal] load build context
 => [1/2] FROM docker.io/library/nginx:alpine
 => [2/2] COPY index.html /usr/share/nginx/html/index.html
 => exporting to image
 => => writing image sha256:748e838dcbd51ef6508f7a88f9c5d2e737ccf928b8e4848d9d8e76e43c82cf02
 => => naming to docker.io/library/my_web:1.0

**docker images**
REPOSITORY    TAG       IMAGE ID       CREATED          SIZE
my_web        1.0       748e838dcbd5   11 seconds ago   62.4MB
nginx         latest    4e5db4761e0f   2 weeks ago      161MB
ubuntu        latest    de7345b16e94   2 weeks ago      100MB
hello-world   latest    e2ac70e7319a   4 months ago     10.1kB

**docker run -d -p 8080:80 --name my_custom_web my_web:1.0**
eb0573108cd54a61265fd74f75f9d13a909afb21116272c4a2a46443f035c610

**docker ps**
**docker logs my_custom_web**
**curl http://localhost:8080**
CONTAINER ID   IMAGE        COMMAND                   CREATED         STATUS         PORTS                                     NAMES
eb0573108cd5   my_web:1.0   "/docker-entrypoint.…"   7 seconds ago   Up 7 seconds   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   my_custom_web
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Configuration complete; ready for start up
2026/07/30 13:02:16 [notice] 1#1: using the "epoll" event method
2026/07/30 13:02:16 [notice] 1#1: nginx/1.31.3
2026/07/30 13:02:16 [notice] 1#1: start worker processes
<h1>Hello Im soyyyyyyyy</h1>

**exit**
