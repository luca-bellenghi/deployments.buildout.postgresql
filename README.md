deployments.buildout.pgbackup
=============================

A buildout template for backing up postgresql

For the impatients
------------------
Those are the commands you want to run
```
virtualenv-2.7 --no-site-packages -p /usr/bin/python2.7 .
. bin activate
ln -s config/base.cfg buildout.cfg
./bin/python2.7 bootstrap.py
./bin/buildout
sudo chown -R postgres. .
sudo cp -i etc/crontab /etc/cron.d/pgbackup
```

Requirements
------------
 - postgres (strange... isn't it?)
 - rsnapshot
 - bzip2

What it gives you?
------------------
This buildout will produce:
 - etc/crontab 
 - bin/backup
 - etc/rsnapshot

### etc/crontab ###
Will launch the backup periodically if correctly installed.
you can install it by running:
```
sudo cp etc/crontab /etc/cron.d/pgbackup
```
### bin/backup ###
The backup script

### etc/rsnapshot ###
Rsnapshot configuration file

Configuritations and options
----------------------------
Take a look in the comments of `config/base.cfg`

TODO
----
Restore script.
