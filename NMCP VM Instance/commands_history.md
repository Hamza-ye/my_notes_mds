### lxc containers list:
+----------+---------+---------------------+------+------------+-----------+
|   NAME   |  STATE  |        IPV4         | IPV6 |    TYPE    | SNAPSHOTS |
+----------+---------+---------------------+------+------------+-----------+
| mis      | RUNNING | 192.168.0.10 (eth0) |      | PERSISTENT | 0         |
+----------+---------+---------------------+------+------------+-----------+
| monitor  | RUNNING | 192.168.0.30 (eth0) |      | PERSISTENT | 0         |
+----------+---------+---------------------+------+------------+-----------+
| pgadmin  | RUNNING | 192.168.0.40 (eth0) |      | PERSISTENT | 0         |
+----------+---------+---------------------+------+------------+-----------+
| postgres | RUNNING | 192.168.0.20 (eth0) |      | PERSISTENT | 0         |
+----------+---------+---------------------+------+------------+-----------+
| proxy    | RUNNING | 192.168.0.2 (eth0)  |      | PERSISTENT | 0         |
+----------+---------+---------------------+------+------------+-----------+
| staging  | RUNNING | 192.168.0.11 (eth0) |      | PERSISTENT | 0         |
+----------+---------+---------------------+------+------------+-----------+

### Main Sudo Account, Out side lxc containers history:
	1 sudo apt-get update && sudo apt-get dist-upgrade
    2  timedatectl set-timezone Asia/Aden
    3  sudo ufw allow ssh
    4  sudo ufw allow 22/tcp comment 'Open port ssh tcp port 22'
    5  sudo ufw disable
    6  sudo ufw enable
    7  git clone https://github.com/bobjolliffe/dhis2-tools-ng.git
    8  cd dhis2-tools-ng/setup
    9  cp configs/containers.json.sample configs/containers.json
   10  vim configs/containers.json
   11  sudo ./lxd_setup.sh
   12  sudo ./install_scripts.sh
   13  sudo lxc list
   14  sudo ./ssl_setup.sh
   15  vim ./ssl_setup.sh
   16  ./ssl_setup.sh
   17  vim ./ssl_setup.sh
   18  sudo ./ssl_setup.sh
   19  sudo dhis2-create-instance dhis2 192.168.0.10 postgres
   20  dhis2-delete-instance dhis2
   21  sudo dhis2-delete-instance dhis2 192.168.0.10 postgres
   22  sudo dhis2-delete-instance dhis2 postgres
   23  sudo lxc list
   24  sudo dhis2-create-instance mis 192.168.0.10 postgres
   25  dhis2-deploy-war -l https://releases.dhis2.org/2.38/dhis2-stable-latest.war mis
   26  clear
   27  exit
   28  dhis2-
   29  dhis2-logview mis
   30  dhis2-deploy-war -l https://releases.dhis2.org/2.38/dhis2-stable-2.38.1.1.war mis
   31  sudo dhis2-create-instance staging 192.168.0.11 postgres
   32  dhis2-deploy-war -l https://releases.dhis2.org/2.38/dhis2-stable-latest.war staging
   33  clear
   34  dhis2-logview mis
   35  clear
   36  curl -sS https://getcomposer.org/installer | php
   37  sudo vim /etc/apache2/sites-enabled/000-default.conf
   38  ls /etc/apache2/sites-enabled/000-default.conf
   39  ls /etc/apache2/sites-enabled
   40  ls
   41  cd dhis2-tools-ng/setup
   42  ls
   43  cd dhis2-tools-ng/
   44  ls
   45  cd ..
   46  ls
   47  cd sudo service apache2 restart
   48  sudo service apache2 restart
   49  clear
   50  udo lxc list
   51  sudo lxc list
   52  lxc-create -n pgadmin-cont -t download
   53  apt install lxc-utils
   54  lxc-create -n pgadmin-cont -t download
   55  apt install lxc1
   56  lxc-create -n pgadmin-cont -t download
   57  apt uninstall lxc-utils
   58  apt install lxc-templates
   59  systemctl status libvirtd
   60  lxc-create -n pgadmin-cont -t download
   61  sudo lxc list
   62  lxc init ubuntu:18.04 pgadmin
   63  sudo lxc list
   64  lxc network attach lxdbr0 pgadmin eth0 eth0
   65  lxc config device set pgadmin eth0 ipv4.address 192.168.0.5
   66  lxc start pgadmin
   67  sudo lxc list
   68  sudo lxc exec pgadmin bash
   69  sudo lxc list
   70  sudo lxc exec postgres bash
   71  sudo dhis2-tomcat-munin staging proxy
   72  sudo lxc exec proxy -- vim /etc/apache2/sites-enabled/apache-dhis2.conf
   73  sudo lxc exec proxy -- ls /etc/apache2/sites-enabled/
   74  sudo lxc exec postgres bash
   75  sudo lxc stop mis
   76  sudo lxc stop staging
   77  sudo lxc restart postgresql
   78  sudo lxc restart postgres
   79  sudo lxc start mis
   80  sudo lxc start staging
   81  ls 
   82  sudo lxc exec proxy bash
   83  ls
   84  cd ..
   85  ls
   86  ls /etc
   87  ls /usr/
   88  ls /usr/bin
   89  clear
   90  cd nmcpye
   91  sudo lxc exec proxy bash
   92  lxc exec proxy -- service apache2 reload
   93  sudo lxc exec proxy bash
   94  sudo lxc list
   95  sudo lxc exec pgadmin bash
   96  sudo lxc exec proxy bash
   97  lxc exec proxy -- service apache2 reload
   98  sudo lxc exec pgadmin bash
   99  sudo lxc exec proxy bash
  100  lxc exec proxy -- service apache2 reload
  101  sudo lxc exec pgadmin bash
  102  sudo lxc exec proxy bash
  103  sudo lxc exec pgadmin bash
  104  sudo lxc exec proxy bash
  105  sudo lxc restart pgadmin
  106  sudo lxc list
  107  sudo lxc exec pgadmin bash
  108  sudo lxc restart pgadmin
  109  sudo lxc exec proxy bash
  110  sudo lxc exec pgadmin bash
  111  sudo lxc restart pgadmin
  112  sudo lxc exec pgadmin bash
  113  sudo lxc restart pgadmin
  114  sudo lxc exec pgadmin bash
  115  sudo lxc restart pgadmin
  116  sudo lxc exec proxy bash
  117  sudo lxc restart pgadmin
  118  sudo lxc exec pgadmin bash
  119  sudo lxc restart pgadmin
  120  sudo lxc exec proxy bash
  121  sudo lxc exec pgadmin bash
  122  sudo lxc restart pgadmin
  123  sudo lxc exec proxy bash
  124  sudo lxc exec pgadmin bash
  125  sudo lxc restart pgadmin
  126  sudo lxc stop pgadmin
  127  sudo lxc remove pgadmin
  128  sudo lxc --help
  129  sudo lxc delete pgadmin
  130  sudo lxc list
  131  lxc init ubuntu:20.04 pgadmin
  132  lxc network attach lxdbr0 pgadmin eth0 eth0
  133  lxc config device set pgadmin eth0 ipv4.address 192.168.0.40
  134  lxc start pgadmin
  135  sudo lxc list
  136  sudo lxc exec pgadmin bash
  137  sudo lxc restart pgadmin
  138  sudo lxc exec proxy bash
  139  sudo lxc exec pgadmin bash
  140  sudo lxc restart pgadmin
  141  sudo lxc exec proxy bash
  142  ls
  143  cd dhis2-tools-ng/setup
  144  ls
  145  sudo ./change_webserver.sh 
  146  sudo lxc list
  147  sudo ./install_scripts.sh
  148  sudo lxc restart proxy
  149  sudo lxc exec proxy bash
  150  sudo ./ssl_setup.sh
  151  sudo lxc exec proxy bash
  152  sudo lxc restart proxy
  153  sudo lxc exec pgadmin bash
  154  sudo lxc restart pgadmin
  155  sudo lxc exec proxy bash
  156  sudo lxc restart proxy
  157  sudo lxc exec proxy bash
  158  sudo lxc restart proxy
  159  sudo lxc list
  160  sudo lxc exec proxy bash
  161  sudo lxc restart proxy
  162  sudo lxc exec proxy bash
  163  sudo lxc restart proxy
  164  vim /etc/nginx/sites-available/dhis2
  165  sudo lxc exec proxy bash
  166  sudo lxc exec postgres bash
  167  sudo lxc restart proxy
  168  sudo lxc exec proxy bash
  169  sudo lxc list
  170  sudo lxc exec postgres bash
  171  sudo lxc exec proxy bash
  172  sudo lxc restart proxy
  173  sudo lxc exec proxy bash
  174  sudo lxc restart proxy
  175  sudo lxc exec proxy bash
  176  sudo lxc restart proxy
  177  sudo lxc exec proxy bash
  178  sudo lxc restart proxy
  179  sudo lxc exec proxy bash
  180  sudo lxc restart proxy
  181  cd dhis2-tools-ng/setup
  182  sudo ./ssl_setup.sh
  183  sudo lxc exec postgres bash
  184  sudo lxc restart proxy
  185  sudo lxc exec postgres bash
  186  sudo lxc restart staging
  187  sudo lxc restart postgres
  188  sudo lxc restart mis
  189  sudo lxc restart staging
  190  sudo lxc restart mis
  191  sudo lxc restart staging
  192  sudo lxc exec proxy bash
  193  histpry
  194  clear
  195  history
  196  ls
  197  cd dhis2-tools-ng/setup
  198  dhis2-delete-instance mis
  199  dhis2-delete-instance mis 192.168.0.10 postgres
  200  sudo lxc list
  201  dhis2-delete-instance staging postgres
  202  sudo dhis2-create-instance mis 192.168.0.10 postgres
  203  sudo lxc delete staging
  204  sudo lxc deletepostgres
  205  sudo lxc delete postgres
  206  sudo lxc list
  207  sudo dhis2-create-instance mis 192.168.0.10 postgres
  208  userdel mis
  209  sudo userdel mis
  210  sudo userdel staging
  211  sudo dhis2-create-instance mis 192.168.0.10 postgres
  212  dhis2-deploy-war -l https://releases.dhis2.org/2.39/dhis2-stable-latest.war mis
  213  sudo dhis2-create-instance staging 192.168.0.11 postgres
  214  dhis2-deploy-war -l https://releases.dhis2.org/2.39/dhis2-stable-latest.war staging
  215  sudo lxc list
  216  history
  217  sudo lxc restart mis
  218  sudo lxc restart staging
  219  sudo lxc restart pgadmin
  220  sudo lxc restart roxy
  221  sudo lxc restart proxy
  222  clear
  223  history
  224  ls
  225  cd ..
  226  ls
  227  cd nmcpye/
  228  ls
  229  cd dhis2-tools-ng/
  230  ls
  231  cd setup/
  232  ls
  233  ./ssl_setup.sh 
  234  clear
  235  history
  236  sudo lxc list
  237  ls
  238  ls /var/lib/ww/html/
  239  sudo lxc exec proxy bash
  240  sudo lxc exec proxy -- vi /var/lib/ww/html/index.html
  241  lxc exec proxy -- service apache2 reload
  242  sudo lxc exec postgres bash
  243  sudo lxc proxy -- sudo
  244  sudo lxc proxy --sudo
  245  sudo lxc exec proxy -- apt update
  246  sudo lxc exec proxy -- sudo --user ubuntu --login
  247  sudo lxc exec proxy bash
  248  history
  249  sudo lxc exec proxy -- vim /etc/apache2/sites-enabled/apache-dhis2.conf
  250  vim /etc/nginx/sites-available/dhis2
  251  sudo lxc exec pgadmin bash
  252  sudo lxc list
  253  sudo lxc exec proxy bash
  254  sudo lxc restart proxy
  255  sudo lxc list
  256  sudo lxc exec proxy bash
  257  history
  258  sudo lxc exec proxy bash
  259  clear
  260  history

### root@proxy lxc container history

    2  ls /etc/nginx/
    3  ls /etc/nginx/upstream/
    4  service nginx reload
    5  ls /etc/nginx/conf.d/
    6  vim /etc/nginx/conf.d/default.conf 
    7  vim /etc/nginx/nginx.conf `
    8  exit
    9  vim /etc/nginx/nginx.conf
   10  systemctl status nginx
   11  exit
   12  ls /etc/nginx/upstream/
   13  vim /etc/nginx/upstream/pgadmin.conf 
   14  systemctl status nginx
   15  service nginx reload
   16  systemctl status nginx
   17  systemctl reload nginx
   18  systemctl status nginx
   19  exit
   20  systemctl status nginx
   21  service nginx reload
   22  systemctl start nginx
   23  systemctl status nginx.service
   24  vim /etc/nginx/upstream/pgadmin.conf 
   25  systemctl start nginx
   26  systemctl status nginx.service
   27  vim /etc/nginx/upstream/pgadmin.conf 
   28  systemctl stop nginx
   29  systemctl status nginx.service
   30  systemctl start nginx
   31  systemctl status nginx.service
   32  vim /etc/nginx/upstream/pgadmin.conf 
   33  systemctl stop nginx
   34  systemctl start nginx
   35  systemctl status nginx.service
   36  vim /etc/nginx/upstream/pgadmin.conf 
   37  systemctl stop nginx
   38  systemctl start nginx
   39  systemctl status nginx.service
   40  vim /etc/nginx/upstream/pgadmin.conf 
   41  systemctl stop nginx
   42  systemctl start nginx
   43  vim /etc/nginx/upstream/pgadmin.conf 
   44  systemctl stop nginx
   45  systemctl start nginx
   46  vim /etc/nginx/upstream/pgadmin.conf 
   47  systemctl stop nginx
   48  systemctl start nginx
   49  vim /etc/nginx/upstream/pgadmin.conf 
   50  systemctl stop nginx
   51  systemctl start nginx
   52  vim /etc/nginx/upstream/pgadmin.conf 
   53  exit
   54  history 
   55  vim /etc/nginx/nginx.conf
   56  ls /etc/nginx/
   57  vim /etc/nginx/nginx.conf
   58  ls /etc/nginx/upstream/
   59  vim /etc/nginx/upstream/mis
   60  vim /etc/nginx/upstream/mis.conf 
   61  vim /etc/nginx/upstream/pgadmin.conf 
   62  systemctl stop nginx
   63  systemctl start nginx
   64  systemctl status nginx.service
   65  exit
   66  vim /etc/nginx/nginx.conf
   67  vim /etc/nginx/upstream/pgadmin.conf 
   68  exit
   69  vim /etc/nginx/upstream/pgadmin.conf 
   70  exit
   71  ls /etc/nginx/
   72  ls /etc/nginx/conf.d/
   73  ls /etc/nginx/conf.d/ssl.conf 
   74  vim /etc/nginx/conf.d/ssl.conf 
   75  vim /etc/nginx/conf.d/ssl-files.conf 
   76  vim /etc/nginx/sec
   77  vim /etc/nginx/conf.d/security.conf 
   78  vim /etc/nginx/upstream/pgadmin.conf 
   79  service nginx restart
   80  exit
   81  vim /etc/nginx/upstream/pgadmin.conf 
   82  service nginx restart
   83  exit
   84  vim /etc/nginx/upstream/pgadmin.conf 
   85  exit
   86  vim /etc/nginx/upstream/pgadmin.conf 
   87  exit
   88  vim /etc/nginx/upstream/pgadmin.conf 
   89  exit
   90  vim /etc/nginx/upstream/pgadmin.conf 
   91  service nginx restart
   92  systemctl status nginx.service
   93  vim /etc/nginx/upstream/pgadmin.conf 
   94  service nginx restart
   95  systemctl status nginx.service
   96  vim /etc/nginx/upstream/pgadmin.conf 
   97  service nginx restart
   98  systemctl status nginx.service
   99  vim /etc/nginx/upstream/pgadmin.conf 
  100  service nginx restart
  101  vim /etc/nginx/upstream/pgadmin.conf 
  102  service nginx restart
  103  vim /etc/nginx/upstream/pgadmin.conf 
  104  service nginx restart
  105  vim /etc/nginx/upstream/pgadmin.conf 
  106  service nginx restart
  107  vim /etc/nginx/upstream/pgadmin.conf 
  108  service nginx restart
  109  vim /etc/nginx/upstream/pgadmin.conf 
  110  exit
  111  vim /etc/nginx/upstream/pgadmin.conf 
  112  service nginx restart
  113  exit
  114  vim /etc/nginx/upstream/pgadmin.conf 
  115  vim /etc/nginx/nginx.conf
  116  ls
  117  ls /var/lib/ww/html/
  118  ls
  119  cd snap/
  120  ls
  121  cd lxd/
  122  ls
  123  cd common/
  124  ls
  125  cd..
  126  cd ..
  127  ls
  128  cd etc
  129  exit
  130  la
  131  ls
  132  cd ..
  133  ls
  134  cd ..
  135  ls
  136  sudo nano /var/www/html/index.html
  137  ls var/www
  138  ls var/
  139  exit
  140  ls
  141  cd snap/
  142  ls
  143  cd lxd/
  144  ls
  145  cd current
  146  ls
  147  cd ..
  148  cd common/
  149  ls
  150  cd ..
  151  ls 23991/
  152  ls 24061/
  153  cd ..
  154  vim /etc/nginx/upstream/pgadmin.conf 
  155  clear
  156  history
  157  vim /etc/nginx/conf.d/default.conf
  158  vim /etc/nginx/nginx.conf
  159  systemctl status nginx
  160  vim /etc/nginx/upstream/pgadmin.conf
  161  exit
  162  ls
  163  sudo su
  164  exit
  165  vim /etc/nginx/nginx.conf
  166  vim /etc/nginx/upstream/pgadmin.conf
  167  vim /etc/nginx/nginx.conf
  168  vim /etc/nginx/upstream/pgadmin.conf
  169  service nginx reload
  170  systemctl status nginx
  171  systemctl stop nginx
  172  systemctl start nginx
  173  systemctl status nginx
  174  exit 
  175  vim /etc/nginx/upstream/pgadmin.conf
  176  systemctl stop nginx
  177  systemctl start nginx
  178  history
  179  vim /etc/nginx/nginx.conf