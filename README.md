# ansible_tester
Ansible test environments using Docker.

# Usage
``` shell
$ git clone git@github.com:zettaittenani/ansible_tester.git
$ cd ansible_tester
$ docker-compose up
$ docker-compose exec controller /bin/bash

## in 'controller' (Docker container) ##

$ cd ansible
$ ansible-playbook -k ./setup.yml -vvv -i ./hosts
$ exit

## end ##

$ docker-compose exec target /bin/bash

## in 'target' (Docker container) ##

$ cat now.txt

## end ##
```
# Ref
- [Ansible controller/target を Docker コンテナで構築する - Qiita](https://qiita.com/zettaittenani/items/4c5844962ae85f851c29)
