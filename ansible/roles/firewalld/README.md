
# This role handles installation of firewalld


# General information

### Switches

* `do_install`: activate all tasks related to installation


# Usage in playbooks :

```

- hosts: test_servers
  remote_user: "{{ansible_remote_user}}"
  become: yes
  become_method: sudo
  roles:
    - role: firewalld
      firewalld_enable: true
      firewalld_rules:
        # open port using required vars only
        - port: "80/tcp"
        # open port using all vars
        - source: "192.168.1.2/24"
          port: "8080/tcp"
          permanent: "yes"
          state: "enabled"
          zone: "public"

```
