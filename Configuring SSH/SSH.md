### Configuring SSH

##### Set hostname and domain name (needed for FQDN)
```
(config)#hostname ExampleHost
(config)# ip domain-name example.com
```

##### Generate RSA Keys - This is the command that will enable SSH 
```
(config)# crypto key generate rsa [modulus len]
```

##### Set SSH to version 2
```
(config)# ip ssh version 2 
```
