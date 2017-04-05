# ansible-role-sshd

## Requirements
- `ansible` >= 2.3
- `python-passlib`

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

## Setup
Change the default password for users

```bash
pip install passlib
python -c "from passlib.hash import sha512_crypt; import getpass; print sha512_crypt.using(rounds=5000).hash(getpass.getpass())"
# Enter password
# Use value to set: `ssh_default_password`
```

## TODO
- [ ] BUG add user needs to be run twice ... ?