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

### SELINUX
 - Security Enhanced Linux
 - 리눅스 커널 보안 모듈
 - 3가지 상태 존재
    + enforcing: 강제
    + permissive: 허용
    + disabled: 비활성화
 - 설정 파일: 해당 파일을 수정하여 상태 변경
```
# /etc/sysconfig/selinux
```
 - 실습때는 일단 비활성화

### 네트워크 설정 변경
 - "# vi /etc/sysconfig/network-scripts/ifconfig-"라고 치고 탭탭하면 네트워크명이 나온다
 - en으로 시작하는 것 선택 후 수정

### Centos7 ip 주소확인
```
# ip a s
# ip addr show
```

### 패키지 설치
```
# yum -y install httpd
# yum install -y openssl mod_ssl
# yum install -y wget elinks git curl lynx tree
# yum install -y mariadb-server mariadb
# yum install -y php php-mysql
```
