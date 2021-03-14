##linux commands
/usr/share/applications
app rename

###find version postgres
sudo -u postgres psql
SELECT version();
SHOW server_version;
psql --version
###
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
#find path
sudo -u postgres psql
SHOW data_directory;
###
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
###Show logs:
tail /opt/sonarqube/logs/sonar.log
###
///////////////////////
###Create user for service
sudo useradd -c "user to run elastic" -d /opt/elastic -g elastic elastic
sudo chown elastic:elastic /opt/elastic -R
sudo groupadd kibana
sudo useradd -c "user to run kibana" -d /opt/kibana -g kibana kibana
sudo chown kibana:kibana /opt/kibana -R 
###
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
###link nginx proxy file
sudo ln -s /etc/nginx/sites-available/elastic.com /etc/nginx/sites-enabled/elastic.com
#service
sudo systemctl reload nginx
###
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
###service systemctl
sudo systemctl daemon-reload
###
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
###find file
find . -name sonarqube-community-branch-plugin-1.6.0.jar
###
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
###Access file
sudo chmod -R 777
#group 
chgrp consult some_dir/ 
chgrp -R consult some_dir/
###
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
###Samba client
smbclient -L //dc -U i.ansari
###
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
###tmux
    Ctrl+b c Create a new window (with shell)
    Ctrl+b w Choose window from a list
    Ctrl+b 0 Switch to window 0 (by number )
    Ctrl+b , Rename the current window
    Ctrl+b % Split current pane horizontally into two panes
    Ctrl+b " Split current pane vertically into two panes
    Ctrl+b o Go to the next pane
    Ctrl+b ; Toggle between the current and previous pane
    Ctrl+b x Close the current pane
###	
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
###Directory 
df -h shows disk space in human-readable format
df -a shows the file system's complete disk usage even if the Available field is 0
du -h 
du -a 
du -s 
stat <file/directory>
fdisk -l shows disk size along with disk partitioning information
#
sudo df -h /var
sudo df -h /var/*

#
cfdisk
sudo cfdisk /dev/sdb
pydf
lsblk
parted -l

https://www.binarytides.com/linux-command-check-disk-partitions/
###
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
###trash-cli
    trash-put: Delete files and folders.
    trash-list: Pint Deleted files and folders.
    trash-restore: Restore a file or folder from trash.
    trash-rm: Remove individual files from the trashcan.
    trash-empty: Empty the trashcan(s).
###	
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
###java 
java -version
update-alternatives --list java
whereis java
sudo apt list --installed
sudo apt list --installed | grep -i openjdk
sudo update-alternatives --config java
###
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
### dpkg: error: dpkg frontend lock is locked by another process###
lsof /var/lib/dpkg/lock
ps cax | grep PID
kill PID
#wait
kill -9 PID
sudo rm /var/lib/dpkg/lock
sudo dpkg --configure -a
###
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
sudo update-alternatives --set java /usr/lib/jvm/jdk-12.0.2/jre/bin/java
sudo update-alternatives --set javac /usr/lib/jvm/jdk-12.0.2/bin/javac
-------------
sudo update-alternatives --install "/usr/bin/java" "java" "/usr/lib/jvm/jdk-12.0.2/bin/java" 1
sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/lib/jvm/jdk-12.0.2/bin/javac" 1
#part one
