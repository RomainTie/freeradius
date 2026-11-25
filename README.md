# Template Instructions

This is a template repository.  Use it to create a new collection in the pfsenible namespace.
Search files for COLLECTION and PACKAGE and replace as appropropriate.  Remove this section when done.

# Ansible Collection - pfsensible.COLLECTION

This is a set of modules to allow you to configure PACKAGE on pfSense firewalls with ansible.

## Installation using ansible galaxy

To install:

```
ansible-galaxy collection install pfsensible.COLLECTION
```

Optionally, you can specify the path of the collection installation with the `-p` option.

```
ansible-galaxy collection install pfsensible.COLLECTION -p ./collections
```

Additionally, you can set the `collections_paths` option in your `ansible.cfg` file to automatically designate install locations.

```ini
# ansible.cfg
[defaults]
collections_paths=collections
```

## Configuration

Current versions of ansible should automatically detect the version of Python on the pfSense system.  If Python discovery fails, you can set
ansible_python_interpreter in your playbook or hosts vars, e.g.:

```
ansible_python_interpreter: /usr/local/bin/python3.11
```

Modules must run as root in order to make changes to the system.  By default pfSense does not have sudo capability so `become` will not work.  You can install it with:
```
  - name: "Install packages"
    package:
      name:
        - pfSense-pkg-sudo
      state: present
```
and then configure sudo so that your user has permission to use sudo.

This package assumes that the PACKAGE pfSense package has been installed.
```
  - name: Install PACKAGE
    package:
      name:
        - pfSense-pkg-PACKAGE
      state: present
```

## Modules
The following modules are currently available:

* [pfsense_COLLECTION](plugins/modules/pfsense_MODULE.py) for configuring PACKAGE

## License

GPLv3.0 or later
