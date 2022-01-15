# Guide to install superset

## Install in Redhat offline

- Create a machine with RHEL 7+ in AWS
- Install Python 3.8+
- Install superset & pymssql
- Find dependencies of Python: `pip freeze > requirement_superset.txt`
- Download all dependencies: `pip download -r requirement_supserset.txt`
- Copy all folder to Machine (ex. to the folder name "superset-redhat"

**In the offline machine**

- Install Python 3.8+
- Create virtual environment & activate it

`python3.8 -m venv venv`
`. venv/bin/activate`

- Install all library Python required by Supserset: `pip install --no-index --find-links ./superset-redhat/ apache-superset`
- Check installation success by: `superset db upgrade`. If there is any error, try to fix with Google & reinstall Python3.8
- Run superset

`superset init`
`superset fab create-admin`

**Attention**: When running superset in host, add parameter `-h 0.0.0.0` when running

`superset run -h 0.0.0.0 -p 8088 --with-threads --reload --debugger`

**Copy logo & superset_config to machine**

- Copy to machine

---

**Other**

- Copy from AWS to local: `scp -i "pem_file.pem" username@host_ip4_public:/home/ec2-user/repos/python-lib.tar.gz .`
- Copy from local to AWS: 
- Copy file asset to asset of Superset:

`cp bic-favicon.png bic-logo-6.png /home/ec2-user/repos/venv/lib/python3.8/site-packages/superset/static/assets`

`export SUPERSET_CONFIG_PATH=superset_config.py`
`superset run -h 0.0.0.0 -p 8088 --with-threads --reload --debugger`

## Install Python3.8

## Install Superset

## Config superset

- Add favicon & icon
- Give access to directory

## Other tricks

### Add favicon in markdown of dashboard: add fa-icon as in html
### Give access by row with user name 

`Row level security` >> Add data access >> `column = '{{current_username()}}'`

### Setup local cache

### Set-up view

### Emoji

We can copy and paste Emoji Icon to dashboard/Chart easily

https://emojikeyboard.org/


