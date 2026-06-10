## CREATE APPLICATION GATEWAY ALONG WITH VMSS
- Step1: Create Application Gateway
- Step2: Create VMSS & add below script to install `apache` & `stress` package
```sh
#!/bin/bash
apt update
apt install apache2 stress -y
echo "WELCOME TO SERVER $(hostname -i)" > /var/www/html/index.html
```
