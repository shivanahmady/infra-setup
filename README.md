**INFRA-SETUP**
============
Ansible playbook to config and deploy docker container app to multiple hosts across multi-envs and ability to provision ec2 instances. 

LOCAL SETUP
============

1. Install Dependencies (requirements.txt)
2. Virtual Env Configuration & Activate

```bash
$ virtualenv  -p python3 venv ----system-site-packages
$ source ./venv/bin/activate
$ pip3 install ansible
$ ansible --version|grep python
```

> ***Virtual Env Bin: ./venv/bin/

3. ansible.cfg

```bash
$ ansible-playbook playbooks/setup_local.yml
```

PLAYBOOK
============
### -- Define Inventory 
- `environments/`
- Inventory organized by environment/functions


### -- Config & Add Host SSH keys
- Ansible uses SSH with public key authentication to connect the deployment host and target hosts.

...

## / / / / / PROVISIONING EC2 INSTANCES \ \ \  \ \ 
### -- Export Security Keys

```bash
export aws_access_key_id = HIDDEN
export aws_secret_access_key = HIDDEN
```


### -- Config Common Role:  
- `/roles/common`
-  language-specific package MGMT 
    - redhat.yml
    - debian.ymls
-  `ansible_os_family`

