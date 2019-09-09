# Docker Compose
```
docker-compose up -d
```

# Navigating OPEN LDAP
Open, https://localhost:6443

Enter the following credentials,
```
Login: cn=admin,dc=example,dc=org
Password: admin
```

For detail information check [this](https://www.youtube.com/watch?v=p857CNi60LM) YouTube video from 06:30 mins onwards.

# Configure LDAP with Identity Server
Put a good **cn** as shown in the diagram:

![](https://github.com/anupamgogoi-wso2/docker-wso2/blob/master/OPEN-LDAP/doc/good-cnmae.png?raw=true)


Check the configuration as shown below,

![](https://raw.githubusercontent.com/anupamgogoi-wso2/docker-wso2/master/OPEN-LDAP/doc/is-config-ldap.png)



# Note
If you are going to use this LDAP for SSO with WSO2 IS, add **displayName** attribute to each user.
