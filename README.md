# ansible-role-sshd

## Install
Add to `requirements.yml`.
```
- name: galaxy.sshd
  src: https://github.com/willfarrell/ansible-role-sshd.git
```

Install Requirements:
`ansible-galaxy install --roles-path=./roles -r requirements.yml`

### authorized_keys
1. Create folder `authorized_keys` at root of playbook.
1. Create files for each user you plan to use inside `authorized_keys`, using `username` as the file name and their public keys as the file contents.
1. Copy folder into role before running. `cp -r authorized_keys roles/galaxy.sshd/files/`

