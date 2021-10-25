Provision macOS systems with Ansible
----

Goal here is to enable easy provisioning of an Apple Mac laptop, etc to be useful.

The main two files are `macos.yml` and `remotes.yml`.

`macos.yml` - playbook to build a macOS system

Using the Ansible Playbook
----
To test the playbook:  
    `ansible-playbook --ask-become-pass -vvvv ./macos.yml --check`

To run it:  
    `ansible-playbook --ask-become-pass ./macos.yml`

Change Log
----
- rewrite of the whole thing to be more modular.
- support roles more effectively by creating roles, and using `import_role` with `tasks_from`
