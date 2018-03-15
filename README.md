# Ansible Examples - Execute a task only one server
How to execute a task on the first, second or other host based in your inventory file

## Pre-reqs

* [ansbile](http://docs.ansible.com/ansible/latest/intro_installation.html)
* [python](https://www.python.org/downloads/)

## Executing the ansible

Command to execute this examples
`ansible-playbook playbook`

## Output

```
PLAY [Examples] **************************************************************************************************

TASK [only_one : Test on the first] ******************************************************************************
skipping: [192.168.0.11]
skipping: [192.168.0.12]
ok:       [192.168.0.10]

TASK [only_one : Test on the second] *****************************************************************************
skipping: [192.168.0.10]
skipping: [192.168.0.12]
ok:       [192.168.0.11]

TASK [only_one : Test on the first] ******************************************************************************
skipping: [192.168.0.11]
skipping: [192.168.0.12]
ok:       [192.168.0.10]

TASK [only_one : List test - second and third] *******************************************************************
skipping: [192.168.0.10] => (item=1) 
skipping: [192.168.0.10] => (item=2) 
skipping: [192.168.0.12] => (item=1) 
ok:       [192.168.0.11] => (item=1)
skipping: [192.168.0.11] => (item=2) 
ok:       [192.168.0.12] => (item=2)

PLAY RECAP *******************************************************************************************************
192.168.0.10             : ok=2    changed=0    unreachable=0    failed=0   
192.168.0.12             : ok=1    changed=0    unreachable=0    failed=0   
192.168.0.11             : ok=2    changed=0    unreachable=0    failed=0   
```