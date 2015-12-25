### Machine provisioning via Ansible yaml files.

Currently, this is just for homebrew with a macbook pro. I assume you've
already installed [Homebrew](http://brew.sh/), and Ansible via `brew install
ansible`.

The *inventory* file has a single entry for localhost.
`python.yml` can be run separately from other playbooks. It will check for
the presence of `pyenv` then install Python 2.7.10, and a collection of 
Python modules.

To test the playbook:
    **ansible-playbook -i inventory --syntax-check --list-tasks -vvvv ./macbook.yml**

To install:
    **ansible-playbook -i inventory ./macbook.yml**



