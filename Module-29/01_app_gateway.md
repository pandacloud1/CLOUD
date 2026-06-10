## AZURE APPLICATION GATEWAY
- Step1.1: CREATE VM
  - Create two Azure VM in different zones
  - Add below script under Advanced --> Custom data
  ```sh
  #!/bin/bash
  apt update
  apt install apache2 -y
  echo "WELCOME TO SERVER $(hostname -i)" > /var/www/html/index.html
  ```
- Step1.2: Create Application Gateway
  - Select Resource Group, Give application gateway name
  - Tier: `Basic`
  - Virtual network: `Default`
  - Subnet: `Create new with different CIDR than VM`
 
- Step2: Create Frontends
  - Add new --> Give name --> Create address

- Step3: Create Backend pool
  - Add backend pool --> Give name
  - Target type: Virtual machine: `Add both VMs`
 
- Step4: Creating Routing rules
  - Rule name: `Give any name`
  - Priority: `1`
  - Listeners: `Give any name`
  - Protocol: `http`; Port: `80`
  - Backend targets: Target type: `Backend pool`
  - Backend target: `Add your backend pool`
  - Backend setting: Add new: `Give any name` --> Add
  - Review & Create

- Step5: Testing
  - Wait for 5-10 mins
  - Get the Application Gateway `Public IP`
  - Access the IP from the browser
