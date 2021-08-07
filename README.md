# ansible-core

Ansible core concepts

- [x] core concepts
- [x] complex include scenarios
- [x] complex role scenarios

## Installation & Basic Configurations

- Install **Ansible** on your local or on a separate server. Run `brew install ansible`, then check `ansible --version`
- Then, Design _inventory_ file to access provisioned machines. Static or dynamic inventory is possible.
- Run, `ansible-playbook FILE_NAME.yaml -i hosts`

## Some Key Concepts

Addition to core capabilities, below topics are critical to understand ansible.

- designing and grouping host file
- become: user delegation (sudo ..)
- localhost vs host : task delegation (where the task will run)
- handling secret things w/ ansible vault

### About roles

- `ansible-galaxy install tansudasli.dummy` to get last version of the role.
- `ansible-playbook run-role_dummy.yaml` to run the role

### About positioning 

There are 3 main steps, and some trade-offs where to use Ansible. So you should consider some critical decisions.

- If you automate _machine preparations_ w/ Ansible, 
then you may be locked w/ vendor specific things (even it is Ansible thing), or maybe it is not worth it to automate at first.
- So Either do it manually or separate this part (1 and 2) from your logic.
- If you need 1000 nodes, you should consider automate 1 and 2 parts (depending on bare metal, or on cloud).
- Some parts of Ansible intersect w/ build tools. If you have gradle, you may not need create container w/ ansible.

1. prepare machines -> get an IP : do it manually at the beginning.
2. pre-configurations on the machines: such as user creations, passwordless-ssh etc... Use _cloud-init_ capability. 
   So you can also run these scripts manually in case you need it.
3. core installations & configs: leverage Ansible

