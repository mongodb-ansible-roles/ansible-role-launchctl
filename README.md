Ansible role for launchctl
==================================

Configures services on MacOS

[![CircleCI](https://img.shields.io/circleci/build/github/mongodb-ansible-roles/ansible-role-launchctl/master?style=flat-square)](https://circleci.com/gh/mongodb-ansible-roles/ansible-role-launchctl)

Requirements
------------

None

Role Variables
--------------

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-------:|:--------:|
| `launchctl_enable_services` | Services to enable on the MacOS host | list | `[]` | false |
| `launchctl_disable_services` | Services to disable on the MacOS host | list | `[]` | false |

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: ansible-role-launchctl
      vars:
        launchctl_enable_services:
          - name: Locate
            service: com.apple.locate
            plist: /System/Library/LaunchDaemons/com.apple.locate.plist
```

Development
-----------

Testing this role locally requires the CircleCI [Local CLI](https://circleci.com/docs/2.0/local-cli/).

To install the CLI for macOS and Linux, invoke the following command:

    $ curl -fLSs https://circle.ci/cli | DESTDIR=/usr/local/bin bash

After installing the CLI, invoke the following command to run the Molecule tests:

    $ make test

License
-------

[Apache License](LICENSE)
