# 和服务器互传文件

## 和服务器互传文件使用scp命令

```
usage: scp [-1246BCpqrv] [-c cipher] [-F ssh_config] [-i identity_file]
           [-l limit] [-o ssh_option] [-P port] [-S program]
           [[user@]host1:]file1 ... [[user@]host2:]file2

```

## 测试1 :在windows mingw终端将文件传到云服务器 

```
$ scp README.md root@116.196.95.101:/root/
The authenticity of host '116.196.95.101 (116.196.95.101)' can't be established.
RSA key fingerprint is SHA256:BUcF1XU+VHOGi8dOJ69fREH+esMF88F/fEv+7A2zqos.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '116.196.95.101' (RSA) to the list of known hosts.
root@116.196.95.101's password:
Permission denied, please try again.
root@116.196.95.101's password:
README.md                                     100
```

## 测试2 :在windows mingw终端从云服务器下载文件



scp命令：scp user@remote.machine:/remote/path /local/path将远程linux主机上/remote/path的文件copy到本主机的/local/path目录
scp /local/path user@remote.machine:/remote/path将本主机的/local/path目录copy到远程linux主机上/remote/path的文件