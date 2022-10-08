# Server_ApacheWebServer

## Setup Server

### hostname
 - hostname 체크
```
$ hostname
```
 - domainname  체크
```
$ dnsdomainname
```
 - hostname setting
```
$ hostnamectl set-hostname master.example.com
$ reboot
```

 - 초기 호스트 파일 체크
   초기에는 위에 등록한 master.example.com이 호스트 파일에 없다
```
$ cat /etc/hosts
```

 - firewall 비활성화
```
systemctl disable firewalld
```


 - NetworkManager 비활성화
```
systemctl disable NetworkManager
```

### ※ 설치: iptables-service
- yum 설치시 -q 옵션은 quite의 약자이다. 화면 로그 없이 설치
```
# yum -q install iptables-services
# service iptables save  # iptable 설정 저장
```

