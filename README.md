# Additional Information
Tunables are based on https://access.redhat.com/documentation/en-us/red_hat_satellite/6.3/html/tuning_red_hat_satellite/tuning#

- Only tested on Satellite 6.3 currently

# Updating Variables
All applicable variables are stored in **./vars/main.yml** and should be reviewed before executing this playbook.

All default variables, which are not likely to change, are stored in **./defaults/main.yml** and should be reviewed before executing this playbook.

# Sample Inventory

```
[satellite]
192.168.89.164
```

# Sample Playbook

```
- hosts: all
  gather_facts: true
  become: false

  roles:

  - foreman_tuning
```

# Sample Usage

```
ansible-playbook -vv my_playbook.yml --ask-pass -u root -t all
```

# Tags
Tags are required in order to execute all or parts of the playbook.  The following tags are permitted:

- all: execute and apply all tunables (listed below)
- dynflow: only apply tunables which affect the Dynflow console
- httpd: only apply tunables which affect Apache
- passenger: only apply tunables which affect Passenger
- postgresql: only apply tunables which affect PostgreSQL
- pulp: only apply tunables which affect Pulp
- tuned: only apply tunables which affect Tuned

