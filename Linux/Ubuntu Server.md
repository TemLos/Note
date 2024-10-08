
# SSH
Port 22
> apt install openssh-server
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
>/opt/alist/`data/config.json`
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
/etc/samba/smb.conf\
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
apt install -y qbittorrent-nox

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

