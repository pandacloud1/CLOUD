# DICTIONARY METHODS

### keys(): Fetch only the keys
```py
cloud = {"AWS": "Amazon", "Azure": "Microsoft", "GCP": "Google", "Salesforce": "SF"}
print(cloud.keys())
```
##### Output
```sh
dict_keys(['AWS', 'Azure', 'GCP', 'Salesforce'])
```

### values(): Fetch only the values
```py
cloud = {"AWS": "Amazon", "Azure": "Microsoft", "GCP": "Google", "Salesforce": "SF"}
print(cloud.values())
```
##### Output
```sh
dict_values(['Amazon', 'Microsoft', 'Google', 'SF'])
```

### items(): Get key‑value pairs in form of tuples
```py
cloud = {"AWS": "Amazon", "Azure": "Microsoft", "GCP": "Google", "Salesforce": "SF"}
print(cloud.items())
```
##### Output
```sh
dict_items([('AWS', 'Amazon'), ('Azure', 'Microsoft'), ('GCP', 'Google'), ('Salesforce', 'SF')])
```

### get(x): Get the value of a key, returns 'NA' if none
```py
cloud = {"AWS": "Amazon", "Azure": "Microsoft", "GCP": "Google", "Salesforce": "SF"}
print(cloud.get("AWS"))
print(cloud.get("Oracle"))
```
##### Output
```sh
Amazon
None
```

### update(x): Update the dictionary & then print it
```py
cloud = {"AWS": "Amazon", "Azure": "Microsoft", "GCP": "Google", "Salesforce": "SF"}
cloud.update({"OCI": "Oracle"})
print(cloud)
```
##### Output
```sh
{'AWS': 'Amazon', 'Azure': 'Microsoft', 'GCP': 'Google', 'Salesforce': 'SF', 'OCI': 'Oracle'}
```

### pop(x): To remove specific key-value & then print the output
```py
cloud = {"AWS": "Amazon", "Azure": "Microsoft", "GCP": "Google", "Salesforce": "SF"}
cloud.pop("Salesforce")
print(cloud)
```
##### Output
```sh
{'AWS': 'Amazon', 'Azure': 'Microsoft', 'GCP': 'Google'}
```

### Get key based on value
- Dictionaries are designed for key → value lookups.
- To get a key from a value, you need to search through `items` & use `for` loop.
```py
cloud = {"AWS": "Amazon", "Azure": "Microsoft", "GCP": "Google", "Salesforce": "CRM"}
for key, value in cloud.items():
    if value == "Amazon":
        print(key)
```
