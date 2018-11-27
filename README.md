### Machine provisioning via Ansible yaml files.

Currently, this is just for homebrew with a macbook pro. I assume you've
already installed [Homebrew](http://brew.sh/), and Ansible via `brew install
ansible`.

The main two files are `macos.yml` and `remotes.yml`.

`macos.yml` - provisions a Mac laptop or desktop.  
`remotes.yml` - provisions a remote workstation or host (not MacOS).  

`macos.yml` can remote provision a host as long as `homebrew` is already installed. So, install that first, then `brew install ansible`.

#### MacOS
To test the playbook:  
    `ansible-playbook -i "localhost," -c local --ask-become-pass -vvvv ./macos.yml --check`

To install:  
    `ansible-playbook -i "localhost," -c local --ask-become-pass ./macos.yml`

#### Remote shell server
Only configures a remote home directory and environment.
    `ansible-playbook -i "<foobar>," ./remotes.yml`

#### Settings.
Set your time zone in `group_vars/all`, default is `America/Los_Angeles`.

Default settings has debug output on.

### Roles
`home` - sets up $HOME with directories and some files  
`macos` - installs software via brew, brew-cask, and adds some taps. Also configures completion.  
`python` - installs [`pyenv`](https://github.com/pyenv/pyenv), and [`pyenv-virtualenv`](https://github.com/pyenv/pyenv-virtualenv).  

### Caveats
Still being worked on, and not complete. Eventually some variables other than `ansible_env.HOME` will be abused.

#### CHANGELOG
- refactoring for Ansible 2.6+
- breaking up home directory tasks
    - ToDo: include roles from above
- move TMUX to its own grouping
- modify modify vars



