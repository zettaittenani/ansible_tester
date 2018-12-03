# ansible_tester
Ansible test environments using Docker.

# Usage
``` shell
$ git clone git@github.com:zettaittenani/ansible_tester.git
$ cd ansible_tester
$ docker-compose up
$ docker-compose exec controller /bin/bash

## in 'controller' (Docker container) ##

#[xxx...] cd ansible
#[xxx...] ansible-playbook -k ./setup.yml -vvv -i ./hosts
#[xxx...] exit

## end ##

$ docker-compose exec target /bin/bash

## in 'target' (Docker container) ##

#[xxx...] cat now.txt

## end ##
```
