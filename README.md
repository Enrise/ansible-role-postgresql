# enrise.postgresql

This is an Ansible task for installing and configuring PostgreSQL, as well as creating databases, users, and user privileges.

## Requirements

- Tested on Ansible 1.5
- Tested on Ubuntu 14.04 (trusty), but it should work on any modern Debian based system.

## Dependencies

- Needs the role `enrise.locale`

## Example playbook

To use this role, build a vars file (vars/php.yml, for example) which you include in your playbook,
which contains something like the following:

    postgresql_users:
      - username: bar
        password: bar

    postgresql_databases:
      - database: bar

    postgresql_privileges:
      - username: bar
        database: bar
        privilege: ALL

    postgresql_additional_packages:
      - postgresql-contrib

Next, you can include the role in your playbook:

    - hosts: all
      sudo: yes
      vars_files:
        - vars/postgresql.yml
      roles:
        - enrise.postgresql

There are a lot of config settings you can overwrite, but you'll have to refer to the file
`defaults/main.yml` to see a list of variables and their description.

## Licence

MIT

## Feedback? Found a bug? Requests?

Let us have it! http://github.com/Enrise/ansible-role-postgresql/issues
