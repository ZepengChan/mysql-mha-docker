# mysql-mha-docker
mysql mha docker compose

## Usage

1. download
```cmd
$ cd /tmp
$ git clone https://github.com/ZepengChan/mysql-mha-docker.git
$ cd mysql-mha-docker

```

2. run containers
```cmd
$ docker-compose up -d

```

3. start ssh service in all containers
```cmd
$ sh ./scripts/ssh_start.sh 

```

4. copy ssh public key to each container

   这里需要进入mha_manager 创建一个文件夹

   
```cmd
$ sudo docker exec -it mha_manager  bash 
$ mkdir /root/mha_share/sshkeys
$ exit
$ sh ./scripts/ssh_share.sh 
```

5. check mha ssh
```cmd
$ sh ./scripts/mha_check_ssh.sh

```

6. set mysql replication (master, backup and slave)
```cmd
$ sh ./scripts/mysql_set_mbs.sh
```

7. check mha repl
```cmd
$ sh ./scripts/mha_check_repl.sh

```

8. start mha manager
```cmd
$ sh ./scripts/mha_start_manager.sh

```
