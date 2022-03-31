## dont forget to set host

how to run

```
ansible-playbook playbookname.yml -f10 -K -k
```

or

```
ansible-playbook -i hosts playbookname.yml --ask-vault-pass --extra-vars='@passwd.yml' -vvv
```

to view password vault

```
ansible-vault view passwd.yml
```

## Important

#### ubuntu ansible role "configuration"
for this rule dont forget to add this file to your home directory
```
grub
rc.local
```
#### Setup Windows machine
make sure preinstalled user set to

```
username: niagahoster
password: ***********
```

#### Editing password variable


```
ansible-vault edit passwd.yml
```

## how to active winrm

open cmd run as administrator
```
curl https://raw.githubusercontent.com/ansible/ansible/devel/examples/scripts/ConfigureRemotingForAnsible.ps1 --output ConfigureRemotingForAnsible.ps1
powershell.exe -ExecutionPolicy ByPass -File ConfigureRemotingForAnsible.ps1
```

if remote host still error make sure windows target open inbound firewall port 5585 and 5586

```
New-NetFirewallRule -DisplayName 'HTTP-Inbound Winrm' -Profile @('Domain', 'Public') -Direction Inbound -Action Allow -Protocol TCP -LocalPort @('5585', '5586')

```
