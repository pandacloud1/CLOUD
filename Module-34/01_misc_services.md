## AZURE DNS

### Webserver script
```sh
#!/bin/bash
apt update -y
apt install apache2 git -y
git clone https://github.com/pandacloud1/webapp2.git && cd webapp2
cp * -R /var/www/html/
```

