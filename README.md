
## Deploy this loopback nodejs APP in AWS Ec2.

```
Welcome to the workshop 
```

- App will use mysqldb
    you have to install & configure MYSQL Database.

- App needs to have nodejs runtime.

- App must have to be started as a appuser.


- Please make sure you have created a seperate directory `/app/` and clone this repo inside.
    - Under `/app/src/<appname>` (Make sure you keep the app name consistent.)
    
- Please make sure this folder is owned by appuser
- No other users  can make any changes to this folder and its files. (They can read but cannot write to this folder. )

- This nodejs Application must be running in port 3000. But this port should not be rechable by anyone.
- You have to protect this port with `ufw` firewall

- Use nginx to do the reverse proxy by Forwarding requests from PORT 80 -> to -> 3000

- If you are using aws make sure you inbounds rules are not allowing 3000 to your Ec2 instance (extra layer of firewall - AWS side)

- Logging :
    - App, once started it should write all the logs under `/app/logs/<appname>/out.log`
    - Both stdout and stderr must be redirected to this log file.





### DB: Install MYSQL & Configure to have this requirements
- Explore how to install mysql database in debain.

`This is your db config for the app to work properly.`

"url": "mysql://appuser:supersecret@mysqldb:3306/sampledb",

```
"mysqldb": {
    "host": "mysqldb",
    "port": 3306,
    "url": "mysql://<DB_USER>:<DB_PASSWORD>@<DOMAIN_NAME_OR_IP_ADDR>:<PORT>/<DATABASE_NAME>",
    "database": "<DATABASE_NAME>",
    "password": "<DB_PASSWORD>",
    "name": "mysqldb",
    "user": "<DB_USER>",
    "connector": "mysql"
  }
```
