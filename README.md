Deploying dictionaries to the jailbroken iOS with Ansible
=========================================================

Ansible role to download and deploy dictionaries for built-in Dictionary.app on iOS.

Create example playbook with following content:

```YAML
- hosts: all
  # Ansible is unable to get facts from iOS, so disable them
  gather_facts: no
  remote_user: mobile

  roles:
  - dictionary

  vars:
  - dictionaries: ['dictd_www.mova.org_slovnyk_en-uk']
```

and run it `ansible-playbook example-playbook.yml -i '192.168.34.109,' --ask-pass`.