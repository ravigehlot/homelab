# Ansible Role: authorized_key

[![Build Status](https://img.shields.io/travis/arillso/ansible.authorized_key.svg?branch=master&style=popout-square)](https://travis-ci.org/arillso/ansible.authorized_key) [![license](https://img.shields.io/github/license/mashape/apistatus.svg?style=popout-square)](https://sbaerlo.ch/licence) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-authorized_key-blue.svg?style=popout-square)](https://galaxy.ansible.com/arillso/authorized_key) [![Ansible Role](https://img.shields.io/ansible/role/d/21612.svg?style=popout-square)](https://galaxy.ansible.com/arillso/authorized_key)

## Description

This role provides secure ssh-client and ssh-server configurations. It is intended to be compliant with the [DevSec SSH Baseline](https://github.com/dev-sec/ssh-baseline).

## Installation

```bash
ansible-galaxy install arillso.authorized_key
```

## Requirements

None

## Role Variables

### authorized_key_users

By default it loads the variable from the user list.
authorized_key_users: '{{ users | default() }}'

#### authorized_key_users Parameters

##### comment

Support: `Windows|Linux`

Change the comment on the public key.
Rewriting the comment is useful in cases such as fetching it from GitHub or GitLab.
If no comment is specified, the existing comment will be kept.

##### exclusive

Support: `Windows|Linux`

Whether to remove all other non-specified keys from the authorized*keys file.
Multiple keys can be specified in a single key string value by separating them by newlines.
This option is not loop aware, so if you use with* , it will be exclusive per iteration of the loop.
If you want multiple keys in the file you need to pass them all to key in a single batch as mentioned above.

##### follow

Support: `Linux`

Follow path symlink instead of replacing it.

##### key

Support: `Windows|Linux`

The SSH public key(s), as a string or url (<https://github.com/username.keys>).

##### key_options

Support: `Windows|Linux`

A string of ssh key options to be prepended to the key in the authorized_keys file.

##### manage_dir

Support: `Windows|Linux`

Whether this module should manage the directory of the authorized key file.
If set to yes, the module will create the directory, as well as set the owner and permissions of an existing directory.
Be sure to set manage_dir=no if you are using an alternate directory for authorized_keys, as set with path, since you could lock yourself out of SSH access.

##### path

Support: `Windows|Linux`

Alternate path to the authorized_keys file.
When unset, this value defaults to ~/.ssh/authorized_keys.

##### state

Support: `Windows|Linux`

Whether the given key (with the given key_options) should or should not be in the file.

##### user

Support: `Windows|Linux`

The username on the remote host whose authorized_keys file will be modified.

##### validate_certs

Support: `Windows|Linux`

This only applies if using a https url as the source of the keys.
If set to no, the SSL certificates will not be validated.
This should only set to no used on personally controlled sites using self-signed certificates as it avoids verifying the source site.

## Dependencies

None

## Example Playbook

```yml
- hosts: all
  roles:
    - arillso.authorized_key
```

## Author

- [Simon Bärlocher](https://sbaerlocher.ch)

## License

This project is under the MIT License. See the [LICENSE](https://sbaerlo.ch/licence) file for the full license text.

## Copyright

(c) 2020, Arilso
