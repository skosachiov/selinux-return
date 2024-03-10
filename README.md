# selinux-return

Automation of Selinux return to some rare national Linux distributions.

## check

`grep CONFIG_SECURITY_SELINUX /boot/config-*`

`# CONFIG_SECURITY_SELINUX is not set` or `CONFIG_SECURITY_SELINUX=y`

## play

`useradd -m ansible`
`passwd ansible`, e.g. 'password
`echo "ansible ALL=(ALL:ALL) ALL" >> /etc/sudoers`
`apt install ansible`

`sshpass -p password ansible-playbook -v --ask-pass -e "ansible_become_password=password" -b -i 192.168.122.244, -u ansible selinux-return.yml`

- logon
- run some soft
- logoff

`sshpass -p password ansible-playbook -v --ask-pass -e "ansible_become_password=password" -b -i 192.168.122.244, -u ansible selinux-enforce.yml`
