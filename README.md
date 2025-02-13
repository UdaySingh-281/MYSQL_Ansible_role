# MYSQL_Ansible_role  

## MySQL Setup using Ansible Roles  

This Ansible role automates the setup of a MySQL Server and configures it for remote access.  

## Requirements  

- Ubuntu-based system with Ansible installed  
- Root or sudo privileges to install packages and modify configurations  

## Role Variables  

The following variables can be modified in `vars/main.yml` or overridden in the playbook:  

| Variable              | Description                     | Default Value      |
|-----------------------|---------------------------------|--------------------|
| `mysql_root_password` | Root password for MySQL        | `sql_root_password` |
| `mysql_db_name`       | Name of the MySQL database     | `chatapp`          |
| `mysql_user`          | Username for the database user | `chatapp_user1`    |
| `mysql_user_password` | Password for the database user | `sql_root_password` |

## Dependencies  

This role does not depend on any external Ansible Galaxy roles.  

## Example Playbook  

Here’s how you can use this role in your playbook:  

```yaml
- hosts: servers
  become: yes
  roles:
    - mysql_ansible_role
```

## Tasks Included
This role performs the following tasks:

- Updates the apt cache
- Installs MySQL Server and PyMySQL
- Configures MySQL to allow remote connections
- Restarts the MySQL service to apply changes
- Creates a MySQL database (chatapp)
- Creates a MySQL user (chatapp_user1) with remote access
- Enables MySQL service to start on boot

## License
BSD

## Author
Created by Uday Singh
