Ansible Role : Postgresqlprivs
=========

Set PostgreSQL Privileges

Requirements
------------

No special requirements; note that this role requires postgresql server up and running on your targets and root access; so either run it in a playbook with a global ```become: yes``` , or invoke the role in your playbook like:

```yaml
- hosts: database
  roles:
    - role: notpixxl.postgresqlprivs
      become: yes
```

Role Variables
--------------

```yaml
# Postgresql Privs to ensure exist.
postgresql_privs: []
# - name: jdoe # required
#   db: somedb # required
#   grant_option: # defaults to 'no'
#   objs: # defaults to not set
#   privs: # defaults to not set
#   schema: # defaults to 'public'
#   login_host: # defaults to 'localhost'
#   login_password: # defaults to not set
#   login_user: # defaults to '{{ postgresql_user }}'
#   login_unix_socket: # defaults to 1st of postgresql_unix_socket_directories
#   port: # defaults to not set
#   type: # defaults to not set
#   state: # defaults to 'present'
```

A list of privileges to ensure exist on the server. Only the ```name``` and the ```db``` is required; all other properties are optional.

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: database
  become: yes
  vars_files:
    - vars/main.yml
  roles:
    - notpixxl.postgresqlprivs
```

Inside ```vars/main.yml```:

```yaml
postgresql_privs
  - name: example_role
    db: example_db
    privs: SELECT,INSERT
    type: table
    objs: example_table1,example_table2
```

License
-------

BSD

Author Information
------------------

christophepiv@gmail.com / https://pixxlisation.tech.blog
