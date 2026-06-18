## AZURE DNS

### Azure SQL Database (Bastion server script)
```sh
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
curl https://packages.microsoft.com/config/ubuntu/22.04/prod.list | sudo tee /etc/apt/sources.list.d/mssql-release.list
sudo apt-get update
sudo ACCEPT_EULA=Y apt-get install -y mssql-tools unixodbc-dev
echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bashrc
source ~/.bashrc
sqlcmd -S <Server-name> -U <username> -P <password>
# You can get the <Server-name> from Azure SQL --> SQL database: <Open your DB> --> Get the <Server-name>
```

### Webserver script
```sh
#!/bin/bash
apt update -y
apt install apache2 git -y
git clone https://github.com/pandacloud1/webapp2.git && cd webapp2
cp * -R /var/www/html/
```

