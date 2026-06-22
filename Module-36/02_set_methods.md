## SET METHODS
- It has set of unique items
- Even if duplicates are added, they will not be printed
- You can filter items based on index

### (add): Add items to set
- Note that the items will be displayed in random order
```py
cloud = {"AWS", "Azure", "GCP", "Salesforce"}

cloud.add("DigitalOcean")
print(cloud)
```
##### Output
```sh
{'Salesforce', 'Azure', 'AWS', 'GCP', 'DigitalOcean'}
```

### (update): Add multiple items to set
- Use [] to add multiple items
```py
cloud = {"AWS", "Azure", "GCP", "Salesforce"}

cloud.update(["DigitalOcean", "IBMCloud", "AlibabaCloud"])
print(cloud)
```
##### Output
```sh
{'AlibabaCloud', 'Azure', 'IBMCloud', 'GCP', 'DigitalOcean', 'Salesforce', 'AWS'}
```
