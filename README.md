{
  "log": {
    "error": "",
    "loglevel": "info",
    "access": ""
  },
  "inbounds": [
    {
      "listen": "0.0.0.0",
      "protocol": "socks",
      "settings": {
        "udp": false,
        "auth": "noauth"
      },
      "port": "1086"
    },
    {
      "listen": "0.0.0.0",
      "protocol": "http",
      "settings": {
        "timeout": 360
      },
      "port": "1087"
    }
  ],
  "outbounds": [
    {
      "mux": {
        "enabled": false,
        "concurrency": 8
      },
      "protocol": "vmess",
      "streamSettings": {
        "wsSettings": {
          "path": "/cdeEyD7R8Z",
          "headers": {
            "host": "www.ijacklin.top"
          }
        },
        "tlsSettings": {
          "serverName": "www.ijacklin.top",
          "allowInsecure": true
        },
        "security": "tls",
        "network": "ws"
      },
      "tag": "proxy",
      "settings": {
        "vnext": [
          {
            "address": "161.35.225.222",
            "users": [
              {
                "id": "59410d86-76c3-4c8d-aee1-87fc954f4380",
                "alterId": 0,
                "level": 0,
                "security": "chacha20-poly1305"
              }
            ],
            "port": 7384
          }
        ]
      }
    },
    {
      "tag": "direct",
      "protocol": "freedom",
      "settings": {
        "domainStrategy": "UseIP",
        "redirect": "",
        "userLevel": 0
      }
    },
    {
      "tag": "block",
      "protocol": "blackhole",
      "settings": {
        "response": {
          "type": "none"
        }
      }
    }
  ],
  "dns": {},
  "routing": {
    "settings": {
      "domainStrategy": "AsIs",
      "rules": []
    }
  },
  "transport": {}
}
