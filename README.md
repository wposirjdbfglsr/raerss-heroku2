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
            "id": "bf0acad3-fc18-43c0-8010-8a26202892e7",
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
                "id": "bf0acad3-fc18-43c0-8010-8a26202892e7"
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

