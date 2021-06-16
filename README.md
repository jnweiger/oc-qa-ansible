# oc-qa-ansible
Playgrund for the ownCloud QA team

Ansible 2.10 is needed for owncloud, ubuntu defaults are too old.

`python3 -m venv ~/ansible && source ~/ansible/bin/activate && pip3 install wheel ansible`

Resolve dependencies before running ansible-playbook.
The following command loads the roles owncloud, redis, apache, php into ~/.ansible/roles/
```
ansible-galaxy install -r roles/requirements.yml
```

Repeat `source ~/ansible/bin/activate` whenever you re-login again.

Run the owncloud playbook (and database, and redis) with the ubuntu group vars:
```
ansible-playbook -i inventories/ubuntu-minimal playbooks/setup.yml
```
