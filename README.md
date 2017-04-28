### Machine provisioning via Ansible yaml files.

Currently, this is just for homebrew with a macbook pro. I assume you've
already installed [Homebrew](http://brew.sh/), and Ansible via `brew install
ansible`.

The main two files are `macos.yml` and `remotes.yml`.

`macos.yml` - provisions a Mac laptop or desktop.
`remotes.yml` - provisions a remote workstation or host.

To test the playbook:
    `ansible-playbook -i "localhost," -c local --ask-become-pass -vvvv ./macos.yml --check`

To install:
    `ansible-playbook -i "localhost," -c local --ask-become-pass ./macos.yml`

### Roles
`home` - sets up $HOME with directories and some files  
`macos` - installs software via brew, brew-cask, and adds some taps  
`python` - installs [`pyenv`](https://github.com/pyenv/pyenv), and [`pyenv-virtualenv`](https://github.com/pyenv/pyenv-virtualenv).  

### Caveats
Stil being worked on, and not complete. Eventually some variables other than `ansible_env.HOME` will be abused.



