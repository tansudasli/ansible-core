# ansible-core

Ansible core concepts

- [x] core concepts
- [x] complex include scenarios
- [x] complex role scenarios


## Installation & Basic Configurations

- Install **Ansible** on your local or on a separate server. Run `brew install ansible`, then check `ansible --version`
- Then, Design _inventory_ file to access provisioned machines. Static or dynamic inventory is possible.
- Run, `ansible-playbook FILE_NAME.yaml -i hosts`

### About roles

- `ansible-galaxy install --force --roles-path /Users/tansudasli/coding/ansible-core tansudasli.role_dummy` to get last version of the role. Adjust the download path
- `ansible-playbook run-role_dummy.yaml` to run the role

