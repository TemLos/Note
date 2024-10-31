# 1panel
Port 5001

Installation
>curl -sSL https://resource.fit2cloud.com/1panel/package/quick_start.sh -o quick_start.sh && sudo bash quick_start.sh
# Alist
Port 5002

User docs
[Home | AList文档](https://alist.nn.ci/zh/)

Installation
>curl -fsSL "https://alist.nn.ci/v3.sh" | bash -s install

Configuration
>vim /opt/alist/`data/config.json`
```
{
  "force": false,
  "site_url": "",
  "cdn": "",
  "jwt_secret": "random_generated",
  "token_expires_in": 48,
  "database": {
    "type": "sqlite3",
    "host": "",
    "port": 0,
    "user": "",
    "password": "",
    "name": "",
    "db_file": "data\\data.db",
    "table_prefix": "x_",
    "ssl_mode": "",
    "dsn": ""
  },
  "meilisearch": {
    "host": "http://localhost:7700",
    "api_key": "",
    "index_prefix": ""
  },
  "scheme": {
    "address": "0.0.0.0",
    "http_port": 5002,
    "https_port": -1,
    "force_https": false,
    "cert_file": "",
    "key_file": "",
    "unix_file": "",
    "unix_file_perm": ""
  },
  "temp_dir": "data\\temp",
  "bleve_dir": "data\\bleve",
  "dist_dir": "",
  "log": {
    "enable": true,
    "name": "data\\log\\log.log",
    "max_size": 50,
    "max_backups": 30,
    "max_age": 28,
    "compress": false
  },
  "delayed_start": 0,
  "max_connections": 0,
  "tls_insecure_skip_verify": true,
  "tasks": {
    "download": {
      "workers": 5,
      "max_retry": 1,
      "task_persistant": true
    },
    "transfer": {
      "workers": 5,
      "max_retry": 2,
      "task_persistant": true
    },
    "upload": {
      "workers": 5,
      "max_retry": 0,
      "task_persistant": false
    },
    "copy": {
      "workers": 5,
      "max_retry": 2,
      "task_persistant": true
    }
  },
  "cors": {
    "allow_origins": [
      "*"
    ],
    "allow_methods": [
      "*"
    ],
    "allow_headers": [
      "*"
    ]
  },
  "s3": {
    "enable": false,
    "port": 5246,
    "ssl": false
  }
}
```

# Samba
Port 445

Configuration
> vim /etc/samba/smb.conf
```
[temp]              <==共享资源名称
        comment = Temporary file space <==简单的解释，内容无关紧要
        path = /tmp     <==实际的共享目录
        writable = yes    <==设置为可写入
        browseable = yes   <==可以被所有用户浏览到资源名称，
        guest ok = yes    <==可以让用户随意登录
```

Tutorial from CSDN
[【Linux】Samba服务器超详细安装、配置（附带各种问题解决方式）\_samba安装-CSDN博客](https://blog.csdn.net/qq_38410730/article/details/80500920)

Set samba user password
> smbpasswd -a username

Restart samba then.
>/etc/init.d/smbd restart
# qBittorrent
Port 5003

Installation
> apt install -y qbittorrent-nox

Config as background program
> vim /etc/systemd/system/qbittorrent-nox.service
```
[Unit]
Description=qBittorrent Command Line Client
After=network.target

[Service]
#Do not change to "simple"
Type=forking
User=orange
#Be careful for UMask when use "root" as user
UMask=007
ExecStart=/usr/bin/qbittorrent-nox -d --webui-port=5003
Restart=on-failure

[Install]
WantedBy=multi-user.target
```
> systemctl daemon-reload
> systemctl start qbittorrent-nox
> systemctl enable qbittorrent-nox
# V2ray

# Clash

# Others
## Disk Mounting
[Ubuntu 配置/etc/fstab参数实现开机自动挂载硬盘\_ubuntu fstab-CSDN博客](https://blog.csdn.net/u010632165/article/details/89597522)
```
# /etc/fstab: static file system information.
#
# Use 'blkid' to print the universally unique identifier for a
# device; this may be used with UUID= as a more robust way to name devices
# that works even if disks are added and removed. See fstab(5).
#
# <file system> <mount point>   <type>  <options>       <dump>  <pass>
# / was on /dev/sda2 during curtin installation

/dev/disk/by-uuid/f85ba1c2-ba10-45ec-ae6c-98a62f0756d4 / ext4 defaults 0 1

# /boot/efi was on /dev/sda1 during curtin installation
/dev/disk/by-uuid/4C5A-5B7B /boot/efi vfat defaults 0 1

/swap.img       none    swap    sw      0       0

/dev/disk/by-id/wwn-0x50014ee2161e90db /mnt/HDD2 auto nosuid,nodev,nofail,x-gvfs-show 0 0

/dev/disk/by-id/wwn-0x50014ee6b35b05b4-part1 /mnt/HDD1 auto nosuid,nodev,nofail,x-gvfs-show 0 0

/dev/disk/by-id/wwn-0x5000c500e7a04a0b /mnt/HDD3 auto nosuid,nodev,nofail,x-gvfs-show 0 0
```
## SSH
Port 22
> apt install openssh-server
## htop
> apt install htop


