**mkdir -p bind_mount_test**
**echo "host original content" > bind_mount_test/data.txt**
**cat bind_mount_test/data.txt**
host original content

**docker run -d --name bind_test -v $(pwd)/bind_mount_test:/data ubuntu sleep infinity**
a942443e7751ba1a4e016149924b1cf57639218e2cb40afe8208004a9dae96e9

**docker exec bind_test cat /data/data.txt**
host original content

**docker exec bind_test bash -c 'echo "modified from container" >> /data/data.txt'**
**cat bind_mount_test/data.txt**
host original content
modified from container

**docker rm -f bind_test**
bind_test

**docker volume create mission_data**
mission_data

**docker volume ls**
DRIVER    VOLUME NAME
local     mission_data

**docker volume inspect mission_data**
[
    {
        "CreatedAt": "2026-08-02T16:05:33+09:00",
        "Driver": "local",
        "Labels": null,
        "Mountpoint": "/var/lib/docker/volumes/mission_data/_data",
        "Name": "mission_data",
        "Options": null,
        "Scope": "local"
    }
]

**docker run -d --name vol_test1 -v mission_data:/data ubuntu sleep infinity**
842fa3fb8f800d66080da56a9a3878e87fa3be217fdb5239c9ba088d2f361de6

**docker exec vol_test1 bash -c 'echo "persistent hello" > /data/hello.txt'**
**docker exec vol_test1 cat /data/hello.txt**
persistent hello

**docker rm -f vol_test1**
vol_test1

**docker volume ls**
DRIVER    VOLUME NAME
local     mission_data

**docker run -d --name vol_test2 -v mission_data:/data ubuntu sleep infinity**
236830c8f441dac2a8b7a31ea789c2477c9fe60748117a9b1295ccb3bc0dd4bc

**docker exec vol_test2 cat /data/hello.txt**
persistent hello

**docker rm -f vol_test2**
vol_test2
