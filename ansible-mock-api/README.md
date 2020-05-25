# Ansible Mock API

An under development API should not block you from writing an Ansible Playbook. Just like regular development, API calls can be mocked with Ansible.
You can toggle mock_mode on and off through command line.


### Usage

Run with mock mode

```sh
$ ansible-playbook playbook.yml -e mock_mode=True
```

Run without mock

```sh
$ ansible-playbook playbook.yml
```