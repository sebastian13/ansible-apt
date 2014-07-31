# Ansible Apt Role

[![Build Status](https://travis-ci.org/weareinteractive/ansible-role-apt.png?branch=master)](https://travis-ci.org/weareinteractive/ansible-role-apt)

> `apt` is an [Ansible](http://www.ansible.com) role which configures apt and installs/updates packages

## Installation

Using `ansible-galaxy`:

```
$ ansible-galaxy install franklinkim.apt
```

Using `arm` ([Ansible Role Manager](https://github.com/mirskytech/ansible-role-manager/)):

```
$ arm install franklinkim.apt
```

Using `git`:

```
$ git clone https://github.com/weareinteractive/ansible-role-apt.git
```

## Variables

```yml
# sets the amount of time the cache is valid
apt_cache_valid_time: 3600
# packages to install
apt_packages: []
# remove packages that are no longer needed for dependencies
apt_autoremove: yes
# remove .deb files for packages no longer on your system
apt_autoclean: yes
# whether or not “suggested” packages should be installed.
apt_install_suggests: false
# whether or not “recommended” packages should be installed.
apt_install_recommends: false
```

## Example playbook

```yml
- host: all
  role: franklinkim.apt
  vars:
    apt_packages:
      - vim
      - openssl
    apt_upgrade: 'no'
    apt_cache_valid_time: 7200 
```

## Testing

```
$ git clone https://github.com/weareinteractive/ansible-role-apt.git
$ cd ansible-role-apt
$ ansible-playbook test.yml
```

## Contributing
[![I Love Open Source](http://www.iloveopensource.io/images/logo-lightbg.png)](http://www.iloveopensource.io/projects/53da2bea87659fce66003fa9)

In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License
Copyright (c) We Are Interactive under the MIT license.
