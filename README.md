# Xray快速部署到Heroku

点击下面按钮部署,好用的话记得点个Star：

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/wposirjdbfglsr/raerss-heroku2.git)


## INBOUND

**streamSettings固定不可更改。**

**prot 固定不可更改。**

vmess+ws+tls(tls由Heroku处理)
```
{
    "listen": "0.0.0.0",
    "port": 12345,
    "protocol": "vmess",
    "settings": {
        "clients": [
            {
            "id": "10caf765-5536-4d0a-9a18-3d64e065484f",
            "level": 0,
            "alterId": 0,
            "email": "love@xray.com"
            }
        ],
        "disableInsecureEncryption": false
    },
    "streamSettings": {
        "network": "ws",
        "security": "none",
        "wsSettings": {
            "acceptProxyProtocol": false,
            "path": "${Xray_Path}"
        }
    }
}
```

vless+ws+tls
```
{
    "listen": "0.0.0.0",
    "port": 12345,
    "protocol": "vless",
    "settings": {
        "clients": [
            {
                "id": "10caf765-5536-4d0a-9a18-3d64e065484f"
            }
        ],
        "decryption": "none"
    },
    "streamSettings": {
        "network": "ws",
        "security": "none",
        "wsSettings": {
            "acceptProxyProtocol": false,
            "path": "${Xray_Path}"
        }
    }
}
```

