
# Installing Jira Software - From archive file

https://confluence.atlassian.com/adminjiraserver/installing-jira-applications-on-linux-from-archive-file-938846844.html

1. Download Jira

https://www.atlassian.com/software/jira/download

Copy to the server, 

[root@192 anup]# ls -ltrh , See if copied

2. Create the installation directory

[root@192 anup]# mkdir <installation-directory>

[root@192 anup]# mkdir jirasoftware


[root@192 anup]# tar -xzf atlassian-jira-software-8.13.2.tar.gz -C <installation-directory>

[root@192 anup]# tar -xzf atlassian-jira-software-8.13.2.tar.gz -C jirasoftware/


[root@192 anup]# cd <installation-directory>

[root@192 anup]# cd jirasoftware/


3. Create the home directory

[root@192 anup]# mkdir jirasoftware-home

[root@192 anup]# mkdir <home-directory>


[root@192 anup]# chown -R user <home-directory>

[root@192 anup]# chmod -R u=rwx,go-rwx <home-directory>

[root@192 anup]# chown -R anup jirasoftware-home/

[root@192 anup]# chmod -R u=rwx,go-rwx jirasoftware-home/


[root@192 jirasoftware]# export JIRA_HOME=/path/to/home-directory

[root@192 jirasoftware]# export JIRA_HOME=/home/anup/jirasoftware-home


Edit <installation-directory>\atlassian-jira\WEB-INF\classes\jira-application.properties

jira.home=/var/jirasoftware-home

[root@192 classes]# pwd

/home/anup/jirasoftware/atlassian-jira-software-8.13.2-standalone/atlassian-jira/WEB-INF/classes

[root@192 classes]# nano jira-application.properties

jira.home=/home/anup/jirasoftware-home


4. Check the ports


Edit <installation-directory>\conf\server.xml

[root@192 atlassian-jira-software-8.13.2-standalone]# pwd

/home/anup/jirasoftware/atlassian-jira-software-8.13.2-standalone

[root@192 atlassian-jira-software-8.13.2-standalone]# nano conf/server.xml

Change the Server port (8005) and the Connector port (8080) to free ports on your server.


5. Start and Stop Jira

[root@192 atlassian-jira-software-8.13.2-standalone]# pwd

/home/anup/jirasoftware/atlassian-jira-software-8.13.2-standalone

[root@192 atlassian-jira-software-8.13.2-standalone]# ./bin/start-jira.sh

[root@192 atlassian-jira-software-8.13.2-standalone]# ./bin/stop-jira.sh

[root@192 atlassian-jira-software-8.13.2-standalone]# ip a

http://Your_IP:8080/
