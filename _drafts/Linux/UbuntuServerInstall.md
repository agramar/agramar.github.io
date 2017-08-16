# Ubuntu Server 16.04 세팅 메뉴얼
1. 우분투 설치 및 부팅용 디스크 만들기
2. 우분투 설치
3. 부팅문제 해결
    - [ ] Ctrl + Alt + F2
    - [ ] root 계정 활성화
    ````
    $ sudo passwd root
    ````
    - [ ] VIM 설치
    ````
    $ sudo apt-get install vim
    ````
    - [ ] GRUB 설정 변경
    ````
    $ sudo vim /etc/default/grub
    ````
    ````
    GRUB_CMD_LINE_LINUX_DEFAULT="nomodeset"
    GRUB_TERMINAL_INPUT="console serial"
    ````
    
4. 프로그램 설치
    - [ ] SSH(Open SSH)
        ````
        # apt-get install open-ssh -y
        ````
    - [ ] FTP(vsftpd)
        1. 설치
        ````
        # apt-get install vsftpd -y
        ````
        2. root 접속 활성화
        ````
        # vim /etc/vsftpd.conf
        #write_enable=YES 주석 해제 
        
        # vim /etc/ftpusers
        root 주석 처리
        
        # service vsftpd restart
        ````
    - [ ] Docker
        ````
        # apt-get install docker.io -y
        ````
    - [ ] Java
        ````
        # apt install default-jdk -y
        # apt install default-jre -y
        ````
    - [ ] Node.js
        ````
        # apt install curl -y
        # curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
        # apt-get install -y nodejs
        ````
    - [ ] Database
        - [ ] MySQL
        - [ ] MariaDB
            1. 설치
            ````
            # apt-get install software-properties-common
            # apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xF1656F24C74CD1D8
            # add-apt-repository 'deb [arch=amd64,i386,ppc64el] http://mirror.jmu.edu/pub/mariadb/repo/10.1/ubuntu xenial main'
            
            # apt update -y
            # apt install -y mariadb-server
            ````
            2. 계정 보안 설정 
        - [ ] MongoDB
            1. 설치
            ````
            # apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
            # echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
            # apt-get update
            # apt-get install -y mongodb-org
            # apt-get install -y mongodb-org=3.2.10 mongodb-org-server=3.2.10 mongodb-org-shell=3.2.10 mongodb-org-mongos=3.2.10 mongodb-org-tools=3.2.10
            
            # echo "mongodb-org hold" | sudo dpkg --set-selections
            # echo "mongodb-org-server hold" | sudo dpkg --set-selections
            # echo "mongodb-org-shell hold" | sudo dpkg --set-selections
            # echo "mongodb-org-mongos hold" | sudo dpkg --set-selections
            # echo "mongodb-org-tools hold" | sudo dpkg --set-selections
            
            # vim /lib/systemd/system/mongod.service
            
            [Unit] 
            Description=High-performance, schema-free document-oriented database 
            After=network.target 
            Documentation=https://docs.mongodb.org/manual 
            
            [Service] 
            User=mongodb 
            Group=mongodb 
            ExecStart=/usr/bin/mongod --quiet --config /etc/mongod.conf 
            
            [Install] 
            WantedBy=multi-user.target
            ````
            2. 계정 보안 설정
            
            3. 외부 접속 설정
            ````
            # vim /etc/mongod.conf
            bind_ip = 0.0.0.0
            ````
            4. 부팅시 서비스 실행 설정
            
        - [ ] PostgreSQL
    - [ ] Http Web Server
        - [ ] Apache2
        - [ ] Nginx
            1. 설치
            ````
            # apt-get install nginx -y
            ````
            2. SSL 설정
            - 존나 안되네 ㅅㅂ
    - [ ] SSL Setting
        1. Certbot-auto 설치(https://certbot.eff.org)
            ````
            $ sudo apt-get update
            $ sudo apt-get install software-properties-common
            $ sudo add-apt-repository ppa:certbot/certbot
            $ sudo apt-get update
            $ sudo apt-get install python-certbot-nginx 
            ````
        2. 인증
            ````
            $ sudo certbot --nginx
            ````
        3. 인증서 자동 갱신(90일마다)
            ````
            $ sudo certbot renew --dry-run
            ````
    - [ ] JSP Server(Apache Tomcat)
    
    
5. 저장소 변경