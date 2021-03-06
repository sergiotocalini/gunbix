# gunbix
Zabbix Agent - Gunicorn

# Dependencies
## Projects
* [Stuffs](https://github.com/sergiotocalini/stuffs/tree/master/gunicorn)

## Packages
* ksh
* sudo
* jq
* curl

__**Debian/Ubuntu**__

```
#~ sudo apt install ksh sudo jq curl
#~
```

__**Red Hat**__
```
#~ sudo yum install ksh sudo jq curl
#~
```

# Deploy
Please the script requires to have already installed the gunicorn init.d script. Follow the README for the other [project](https://github.com/sergiotocalini/stuffs/tree/master/gunicorn).

## Zabbix
Zabbix user has to have sudo privileges.

```
#~ cat /etc/sudoers.d/user_zabbix
# Allow the user zabbix to execute any command without password
zabbix	ALL=(ALL:ALL) NOPASSWD:ALL
```

Then you can run the deploy_zabbix script

```
#~ git clone https://github.com/sergiotocalini/gunicorn.git
#~ sudo ./gunicorn/deploy_zabbix.sh
#~ sudo systemctl restart zabbix-agent
```

*Note: the installation has to be executed on the zabbix agent host and you have to import the template on the zabbix web. The default installation directory is /etc/zabbix/scripts/agentd/gunicorn/*
