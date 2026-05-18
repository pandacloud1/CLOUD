## COMMANDS TO SSH FROM SERVER-1 TO SERVER-2
- We need to have the destination Server key in our existing server
- The key must have executable permissions allowed only to the user

### Manually create pem key
```sh
vi <Server-2-key>.pem
# Paste the pem key content
# Press 'Esc' --> ':wq' to exit the editor
```

### Give executable permissions to the key only for the user
```sh
chmod 700 <Server-2-key>.pem
```

### SSH from Server-1 --> Server-2
```sh
ssh -i <Server-2-key> <Server2-user>@<Server-2-PrivateIP>
# eg.
ssh -i Server2.pem ec2-user@10.0.1.25
```
