# Answers

    # -------------------------
    Calixte Melly
    Nguyen-Phuong, Le

    We certify that we have done all the lab tasks and we have a running environment on our 
    machine to prove it. We are ready to demonstrate it at any time and to explain the process
    we have followed.
    # -------------------------------

    # -- YOUR ANSWER TO QUESTION 1 --

     C:\Users\Calixte\Documents\GitHub\Teaching-HEIGVD-RES-MonSys\monsys-web-infra> vagrant up
    Bringing machine 'default' up with 'virtualbox' provider...
    > default: Box 'phusion-open-ubuntu-14.04-amd64' could not be found. Attempting to find and install...
      default: Box Provider: virtualbox
      default: Box Version: >= 0
    > default: Adding box 'phusion-open-ubuntu-14.04-amd64' (v0) for provider: virtualbox
      default: Downloading: https://oss-binaries.phusionpassenger.com/vagrant/boxes/latest/ubuntu-14.04-amd64-vbox.box
      default: Progress: 100% (Rate: 2259k/s, Estimated time remaining: --:--:--)
    > default: Successfully added box 'phusion-open-ubuntu-14.04-amd64' (v0) for 'virtualbox'!
    > default: Importing base box 'phusion-open-ubuntu-14.04-amd64'...
    > default: Matching MAC address for NAT networking...
    > default: Setting the name of the VM: monsys-web-infra_default_1399532582418_97066
    > default: Clearing any previously set forwarded ports...
    > default: Clearing any previously set network interfaces...
    > default: Preparing network interfaces based on configuration...
      default: Adapter 1: nat
      default: Adapter 2: hostonly
    > default: Forwarding ports...
      default: 9090 => 8080 (adapter 1)
      default: 22 => 2222 (adapter 1)
    > default: Booting VM...
    > default: Waiting for machine to boot. This may take a few minutes...
      default: SSH address: 127.0.0.1:2222
      default: SSH username: vagrant
      default: SSH auth method: private key
      default: Warning: Connection timeout. Retrying...
    > default: Machine booted and ready!
    > default: Checking for guest additions in VM...
    > default: Configuring and enabling network interfaces...
    > default: Mounting shared folders...
      default: /vagrant => C:/Users/Calixte/Documents/GitHub/Teaching-HEIGVD-RES-MonSys/monsys-web-infra
    > default: Running provisioner: shell...
      default: Running: inline script
    > default: stdin: is not a tty
    > default: Cleaning up Docker containers...
    > default: /tmp/vagrant-shell: line 2: docker: command not found
    > default: /tmp/vagrant-shell: line 3: docker: command not found
    > default: /tmp/vagrant-shell: line 4: docker: command not found
    > default: /tmp/vagrant-shell: line 5: docker: command not found
    > default: /tmp/vagrant-shell: line 6: docker: command not found
    > default: /tmp/vagrant-shell: line 7: docker: command not found
    > default: /tmp/vagrant-shell: line 8: docker: command not found
    > default: /tmp/vagrant-shell: line 9: docker: command not found
    > default: Running provisioner: docker...
      default: Installing Docker (latest) onto machine...
      default: Configuring Docker to autostart containers...
    > default: Building Docker images...
    > default: -- Path: /vagrant/docker/rp-nginx
    > default: -- Path: /vagrant/docker/web-apache
    > default: -- Path: /vagrant/docker/app-nodejs
    > default: Starting Docker containers...
    > default: -- Container: rp-node
    > default: -- Container: web-node-1
    > default: -- Container: web-node-2
    > default: -- Container: app-node

    # -------------------------------

    # -- YOUR ANSWER TO QUESTION 2 --
    vagrant@ubuntu-14:~$ uname -a
    Linux ubuntu-14 3.13.0-24-generic #46-Ubuntu SMP Thu Apr 10 19:11:08 UTC 2014 x86_64 x86_64 x86_64 GNU/Linux
    # -------------------------------

    # -- YOUR ANSWER TO QUESTION 3 --
    REPOSITORY          TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
    heig/app-nodejs     latest              3038a15648dc        12 minutes ago      398.9 MB
    heig/web-apache     latest              164e67ff70ba        15 minutes ago      411.9 MB
    heig/rp-nginx       latest              97d4d78bafb0        18 minutes ago      637.9 MB
    dockerfile/ubuntu   latest              cbc81be8f75e        12 days ago         378.6 MB
    # -------------------------------

    # -- YOUR ANSWER TO QUESTION 4 --
    CONTAINER ID        IMAGE                    COMMAND                CREATED             STATUS              PORTS
               NAMES
    5e500e39d10e        heig/app-nodejs:latest   node /opt/server.js    28 seconds ago      Up 27 seconds       0.0.0.0:7070
    ->80/tcp   app-node
    2469649f285c        heig/web-apache:latest   /usr/sbin/apache2ctl   28 seconds ago      Up 28 seconds       0.0.0.0:8082
    ->80/tcp   web-node-2
    ee4e6a8d8a49        heig/web-apache:latest   /usr/sbin/apache2ctl   29 seconds ago      Up 29 seconds       0.0.0.0:8081
    ->80/tcp   web-node-1
    2964da455198        heig/rp-nginx:latest     /opt/init.sh           30 seconds ago      Up 29 seconds       0.0.0.0:9090
    ->80/tcp   rp-node
    # -------------------------------

    # -- YOUR ANSWER TO QUESTION 5 --
    Web-node-1
     "NetworkSettings": {
         "IPAddress": "172.17.0.3",
         "IPPrefixLen": 16,
         "Gateway": "172.17.42.1",
         "Bridge": "docker0",
         "PortMapping": null,
         "Ports": {
             "80/tcp": [
                 {
                     "HostIp": "0.0.0.0",
                     "HostPort": "8081"
                 }
             ]
         }
     },
     Web-node-2
      "NetworkSettings": {
         "IPAddress": "172.17.0.4",
         "IPPrefixLen": 16,
         "Gateway": "172.17.42.1",
         "Bridge": "docker0",
         "PortMapping": null,
         "Ports": {
             "80/tcp": [
                 {
                     "HostIp": "0.0.0.0",
                     "HostPort": "8082"
                 }
             ]
         }
     }
     
     rp-node
     "NetworkSettings": {
        "IPAddress": "172.17.0.2",
        "IPPrefixLen": 16,
        "Gateway": "172.17.42.1",
        "Bridge": "docker0",
        "PortMapping": null,
        "Ports": {
            "80/tcp": [
                {
                    "HostIp": "0.0.0.0",
                    "HostPort": "9090"
                }
            ]
        }
    }

    app-node

    "NetworkSettings": {
        "IPAddress": "172.17.0.5",
        "IPPrefixLen": 16,
        "Gateway": "172.17.42.1",
        "Bridge": "docker0",
        "PortMapping": null,
        "Ports": {
            "80/tcp": [
                {
                    "HostIp": "0.0.0.0",
                    "HostPort": "7070"
                }
            ]
        }
    }
    # -------------------------------

    # -- YOUR ANSWER TO QUESTION 6 --

    Host (your laptop):
    - IP address: 10.192.87.11

    Virtual Machine run by Virtual Box
    - IP address: 10.0.2.15
    - PAT: packets arriving on 10.192.87.11:8080 are forwarded to 10.0.2.15:9090

    Docker Bridge
    - IP address: DB.DB.DB.DB
    - PAT: packets arriving on 172.17.42.1:7070 are forwarded to 172.17.42.5:80
    - PAT: packets arriving on 172.17.42.1:8082 are forwarded to 172.17.42.4:80
    - PAT: packets arriving on 172.17.42.1:8081 are forwarded to 172.17.42.3:80
    - PAT: packets arriving on 172.17.42.1:9090 are forwarded to 172.17.42.2:80

    Docker Container 1
    - IP address: 172.17.42.5

    Docker Container 2
    - IP address: 172.17.42.4

    Docker Container 3
    - IP address: 172.17.42.3

    Docker Container 4
    - IP address: 172.17.42.2

    # -------------------------------

    # -- YOUR ANSWER TO QUESTION 7 --

    Which command did you type on the terminal to establish the connection?
        -telnet www.monsys.com 9090

    What HTTP request did you type and send?
        -GET / HTTP/1.1
        -host: www.monsys.com
        (CRLF)

    What HTTP response did you get?
    # -------------------------------

HTTP/1.1 200 OK Server: nginx/1.6.0 Date: Sun, 25 May 2014 11:37:12 GMT
Content-Type: text/html Content-Length: 1538 Connection: keep-alive
X-Powered-By: PHP/5.5.9-1ubuntu4 Vary: Accept-Encoding

Welcome To MonSys Front-End

                <script language="JavaScript">

                        $(document).ready(function () {
                                refreshNodes();
                        });

                        function refreshNodes() {
                            $.getJSON('/ajax/resources/nodes',
                            function(data) {
                                var items = [];

                                $.each(data,
                                function(key, val) {
                                    items.push('<li>' + val.name + ", " + val.description + ", load: " + val.currentLoad

Level + ' %

'); });

                                $('#monitor').html("<ul>" + items.join('') + "</ul>");
                            });
                                var t=setTimeout("refreshNodes()", 1000);
                        }
        </script>
        </head>
        <body>
                <h1>Welcome to MonSys</h1>
                <h2>You are connected to the front-end system, implemented in PHP</h2>
                <b>Note</b>: this page is sending HTTP GET requests to <verbatim>/ajax/resources/nodes</verbatim> in ord

er to retrieve JSON representations of the resources managed by the
back-end.

                <div id="monitor">
                        You should monitoring data coming from the back-end here.
                </div>

                <br/>
                Brought to you by the University of Applied Sciences of Western Switzerland
        </body>

    # -- YOUR ANSWER TO QUESTION 8 --

    Which command did you type on the terminal to establish the connection?
        -telnet www.monsys.com 9090
        
    What HTTP request did you type and send?
        -GET /ajax/ressources/nodes HTTP/1.1
        -host: www.monsys.com
        (CRLF)

    What HTTP response did you get?
    # -------------------------------

HTTP/1.1 200 OK Server: nginx/1.6.0 Date: Sun, 25 May 2014 11:39:51 GMT
Content-Type: application/json Transfer-Encoding: chunked Connection:
keep-alive

fb [{"name":"P-001","description":"Epson
Printer","currentLoadLevel":62.515123072080314},{"name":"P-002","description":"Can
on
Printer","currentLoadLevel":84.90090079139918},{"name":"P-003","description":"HP
Printer","currentLoadLevel":55.61101 429630071}] 0

    # -- YOUR ANSWER TO QUESTION 9 --

    Check IP with : 
        docker inspect web-clash-X
        => 172.17.0.6 - 172.17.0.7 - 172.17.0.8

        
    Check if server respond :

    LIVE

    PS C:\Users\Calixte> telnet live.clashofclasses.ch 8014
    Trying 192.168.33.20...
    Connected to live.clashofclasses.ch.
    Escape character is '^]'.
    GET / HTTP
    HTTP/1.1 400 Bad Request
    Server: nginx/1.6.0
    Date: Sun, 25 May 2014 12:25:50 GMT
    Content-Type: text/html
    Content-Length: 172
    Connection: close

    <html>
    <head><title>400 Bad Request</title></head>
    <body bgcolor="white">
    <center><h1>400 Bad Request</h1></center>
    <hr><center>nginx/1.6.0</center>
    </body>
    </html>

    DASHBOARD

    PS C:\Users\Calixte> telnet dashboard.clashofclasses.ch 8014
    Trying 192.168.33.20...
    Connected to dashboard.clashofclasses.ch.
    Escape character is '^]'.
    GET / HTTP
    HTTP/1.1 400 Bad Request
    Server: nginx/1.6.0
    Date: Sun, 25 May 2014 12:27:50 GMT
    Content-Type: text/html
    Content-Length: 172
    Connection: close

    <html>
    <head><title>400 Bad Request</title></head>
    <body bgcolor="white">
    <center><h1>400 Bad Request</h1></center>
    <hr><center>nginx/1.6.0</center>
    </body>
    </html>

    # -------------------------------
    # -- YOUR ANSWER TO QUESTION 10 --

    fichier host :
    192.168.33.20   live.clashofclasses.ch
    192.168.33.20   dashboard.clashofclasses.ch


    Check telnet connection and hand-crafted http request:

PS C:\> telnet live.clashofclasses.ch 8014 Trying 192.168.33.20...
Connected to live.clashofclasses.ch. Escape character is '\^]'. GET /
HTTP/1.1 host: live.clashofclasses.ch

HTTP/1.1 200 OK Server: nginx/1.6.0 Date: Sun, 25 May 2014 14:09:45 GMT
Content-Type: text/html Content-Length: 2058 Connection: keep-alive
Last-Modified: Thu, 15 May 2014 06:49:24 GMT ETag: "80a-4f96ab288c500"
Accept-Ranges: bytes Vary: Accept-Encoding

Sticky Footer Template for Bootstrap

    <!-- Bootstrap core CSS -->
    <link href="./css/live-bootstrap.css" rel="stylesheet">

    <!-- Custom styles for this template -->
    <link href="./css/sticky-footer.css" rel="stylesheet">

    <!-- Just for debugging purposes. Don't actually copy this line! -->
    <!--[if lt IE 9]><script src="../../assets/js/ie8-responsive-file-warning.js"></script><![endif]-->

    <!-- HTML5 shim and Respond.js IE8 support of HTML5 elements and media queries -->
    <!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/libs/html5shiv/3.7.0/html5shiv.js"></script>
      <script src="https://oss.maxcdn.com/libs/respond.js/1.4.2/respond.min.js"></script>
    <![endif]-->

    <!-- Begin page content -->
    <div class="container">
      <div class="page-header">
        <h1>Welcome To Clash of Classes!</h1>
      </div>
      <p class="lead">This is the Welcome Page for the <b>live</b> section of the website, which is accessible at this U

RL http://live.clashofclasses.ch.

You can jump to the dashboard section of the website here.

        <p></p>
                <img src="success.jpg" width="300">
        <p></p>


    </div>


    <div id="footer">
      <div class="container">
        <p class="text-muted">We <i class="fa fa-heart"></i> Application Level Protocols</p>
      </div>
    </div>


    <!-- Bootstrap core JavaScript
    ================================================== -->
    <!-- Placed at the end of the document so the pages load faster -->

PS C:\> telnet dashboard.clashofclasses.ch 8014 Trying 192.168.33.20...
Connected to dashboard.clashofclasses.ch. Escape character is '\^]'. GET
/ HTTP/1.1 host: dashboard.clashofclasses.ch

HTTP/1.1 200 OK Server: nginx/1.6.0 Date: Sun, 25 May 2014 14:12:09 GMT
Content-Type: text/html Content-Length: 2057 Connection: keep-alive
Last-Modified: Thu, 15 May 2014 06:49:24 GMT ETag: "809-4f96ab288c500"
Accept-Ranges: bytes Vary: Accept-Encoding

Sticky Footer Template for Bootstrap

    <!-- Bootstrap core CSS -->
    <link href="./css/dashboard-bootstrap.css" rel="stylesheet">

    <!-- Custom styles for this template -->
    <link href="./css/sticky-footer.css" rel="stylesheet">

    <!-- Just for debugging purposes. Don't actually copy this line! -->
    <!--[if lt IE 9]><script src="../../assets/js/ie8-responsive-file-warning.js"></script><![endif]-->

    <!-- HTML5 shim and Respond.js IE8 support of HTML5 elements and media queries -->
    <!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/libs/html5shiv/3.7.0/html5shiv.js"></script>
      <script src="https://oss.maxcdn.com/libs/respond.js/1.4.2/respond.min.js"></script>
    <![endif]-->

    <!-- Begin page content -->
    <div class="container">
      <div class="page-header">
        <h1>Clash of Classes Dashboard</h1>
      </div>
      <p class="lead">This is the Welcome Page for the <b>dashboard</b> section of the service, which is accessible at t

his URL http://dashboard.clashofclasses.ch

You can go back to the live section here.

    </div>

    <div id="footer">
      <div class="container">
        <p class="text-muted">We <i class="fa fa-heart"></i> Application Level Protocols Teachers</p>
      </div>
    </div>


    <!-- Bootstrap core JavaScript
    ================================================== -->
    <!-- Placed at the end of the document so the pages load faster -->

\`\`\` \

Nous avons ensuite testé l'affichage dans un navigateur. Voir capture d'écran dans le dossier screenshot.



# -------------------------------
