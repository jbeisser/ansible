### Machine provisioning via Ansible yaml files.

Currently, this is just for homebrew with a macbook pro. I assume you've
already installed [Homebrew](http://brew.sh/), and Ansible (via *brew install
ansible*).

The *inventory* file has a single entry for localhost.

To test the playbook:
    **ansible-playbook -i inventory --syntax-check --list-tasks -vvvv ./macbook.yml**


