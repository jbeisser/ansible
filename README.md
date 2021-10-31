Provision macOS systems with Ansible
----

Goal here is to enable easy provisioning of an Apple Mac laptop, etc to be useful.

The only real playbook is `macos.yml`

This set up does NOT consider operating systems outside of MacOS at this time.

`macos.yml` - playbook to build a macOS system. 

Using the Ansible Playbook
----
To test the playbook:  
    `ansible-playbook --ask-become-pass -vvvv ./macos.yml --check`

To run it:  
    `ansible-playbook --ask-become-pass ./macos.yml`

Explanations of roles
----
`common`: basic pieces of software that are on every macOS system  
`macos`: basic settings for a macOS system. Configure brew, set screensaver behavior, etc  
`desktop`: default utilities for desktop systems  
`laptop`: default utilities for laptops  
`home`: configure home directory and files  
`devel`: install development tools (intellij, etc)  
`wifi`:  install WiFi specific tools  
`utils`: collected tasks for GUI utilities  
`tools`: collected tasks for CLI utilities  
`vm`: install VM utilities (VirtualBox, vagrant)  
`docker`: install Docker for Desktop etc  



Change Log
----
- unify various pieces under tools/utils that are specifically for software, etc.
- have "devel" be the developer role for devices.
- rewrite of the whole thing to be more modular.
- support roles more effectively by creating roles, and using `import_role` with `tasks_from`
