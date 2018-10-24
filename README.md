## dokku_cheatsheet
Cheatsheet of Dokku commands


**Predeploy:**
(clientside)
```
.gitignore

Procfile 
> web:gunicorn app:app

runtime.txt
> python-3.6.6

requirements.txt
> pip freeze > requirements.txt
```

**DB:**
(serverside)
```
Create Postgres DB:
> dokku postgres:create <db>
  
Link Postgres DB to app:
> dokku postgres:link <db> <app>
```
**Post Deployment:**
(serverside)
```
Run python shell:
> dokku run <app> python
  
Run python script:
> dokku run <app> python <filename>.py

Set Config/env variables:
> dokku config:set <app> <var>
> eg: dokku config:set myapp apikey=123

Set Domain:
> dokku domain:set <app> <url>

SSL Certification:
> dokku config:set --no-restart <app> DOKKU_LETSENCRYPT_EMAIL=<emailaddress>
> dokku letsencrypt <app>
```
