# playbooks

These are my playbooks to automate my development environment on my laptop, HP running Ubuntu 16.04

## Using these playbooks

The default user the playbooks use is the vagrant user, since I first wrote and tested these on a vagrant vm.
You can pass your own username in using the --extra-vars argument

example:

```
ansible-playbook sw-installation.yml --extra-vars "username=tom"
```

## The order these playbook should be executed in:

1. update-ansible-playbook.yml
..* so that the latest version of ansible is installed on the machine
2. ssh-keys-setup.yml
..* the keys need to be generated first and uploaded to github manually before anything can be cloned.
..* this playbook proved problematic so I ended up doing it manually
3. sw-installation.yml
..* this playbook installs all the software I use
4. sw-configuration.yml
..* this playbook configures a lot of the installed software
