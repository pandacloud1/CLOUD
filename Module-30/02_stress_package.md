## RUNNING STRESS COMMAND
- Stress is already installed using custom data
- Run this command in both VMs part of your VMSS to increase the CPU
### Increase CPU using stress package
```sh
stress --cpu 400
```
- You can directly upload the key in MobaXterm or use below steps for pem key creation
  
### Create pem key in VM
```sh
vi <key-name>.pem
# Paste key content & press Esc --> :wq (Hit Enter)
```

### Give executable permission to the pem key
```sh
chmod 7000 <key-name>.pem
```

### Access VMSS from Bastion
```sh
sudo ssh -i <key-name>.pem azureuser@<private-ip>
```

Note:
- Wait for 5-10 mins & check `Percentage CPU` from VMSS --> Monitoring --> Metrics
- Also the email notifications must be triggered if CPU crosses the threshould
