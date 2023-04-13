Content for Jenkins Execute Shell:
mv HTMLPage1.html index.html
sshpass -p "docker" scp -r index.html root@web:/usr/local/apache2/htdocs/index.html