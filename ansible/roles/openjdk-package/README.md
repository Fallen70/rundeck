
# Role openjdk (package manager installation)


## Role usage

```yml

- hosts: openjdk_package_servers
  remote_user: "{{ansible_remote_user}}"
  become: yes
  become_method: sudo
  roles:
    - role: openjdk-package
      openjdk_version_major: 8


```
