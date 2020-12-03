app-automysqlbackup
=========

A role to install the [automysqlbackup](https://sourceforge.net/projects/automysqlbackup/) script for managing `mysqldump` backups.

Role Variables
--------------

`mysql_port` (int): The port used by the MySQL instance that is to be backed up.

`automysqlbackup_clone_repo` (string) : An HTTP URL to a Git repo to be downloaded.  An SSH user@host:path form can be used if SSH keys are set up in an independent task/role/playbook.

`automysqlbackup_version` (string) : The tagged release to check out.

`automysqlbackup_service_account` (string) : The name of a service account to run `automysqlbackup` / perform MySQL backups.

`automysqlbackup_home_dir` (string) : The home directory for a service account.

`automysqlbackup_config_path` (string) : The path to where the `automysqlbackup` config should be stored.

`automysqlbackup_config` (dict) : A dictionary whose keys map to the variables that should be defined in the `automysqlbackup` config.  Keys have an isomorphic mapping to the `automysqlbackup` config and use the same strings.

`automysqlbackup_prebackup` (string) : An inline script to run before backups.  Must be configured in `automysqlbackup_config`.  The path where the script is place is the path defined by `CONFIG_prebackup`.

`automysqlbackup_postbackup` (string) : An inline script to run after backups.  Must be configured in `automysqlbackup_config`.  The path where the script is place is the path defined by `CONFIG_postbackup`.

`automysqlbackup_cron_minute` (int) : The minute used by a cron job that runs `automysqlbackup`.

`automysqlbackup_cron_hour` (int) : The minute used by a cron job that runs `automysqlbackup`.

`automysqlbackup_cron_day` (int) : The minute used by a cron job that runs `automysqlbackup`.

`automysqlbackup_cron_month` (int) : The minute used by a cron job that runs `automysqlbackup`.

`automysqlbackup_cron_weekday` (int) : The minute used by a cron job that runs `automysqlbackup`.


Dependencies
------------

It is recommended that you run the [ansible-role-mysql](https://github.com/geerlingguy/ansible-role-mysql) beforehand.  We've renamed this to `app-mysql` for our infrastructure as part of our naming convention.

License
-------

Revised 3-Clause BSD License
