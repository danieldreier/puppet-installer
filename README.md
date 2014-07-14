Puppet Install Script
=============================
[![Build Status](https://travis-ci.org/danieldreier/puppet-installer.svg?branch=master)](https://travis-ci.org/danieldreier/puppet-installer)

####Table of Contents

1. [Overview](#overview)
4. [Usage](#usage)
    * [What this module affects](#what-this-module-affects)
5. [Limitations - OS compatibility, etc.](#limitations)
7. [Credits](#credits)

##Overview

This is a puppet install script to install puppet on most common Linux distros.
The purpose of this is to avoid re-writing the install script for every small
project.

The install script is tested on:
- arch
- centos6
- centos7
- debian-squeeze
- debian-wheezy
- fedora20
- ubuntu1204
- ubuntu1404

Tests are run in a docker environment in travis ci with every commit. Please
report any problems you encounter as issues on the projet's github issue tracker.


##Usage
Usage is simple. You can run without parameters:
```bash
$ ./install_puppet.sh
```

Alternatively, you can specify a desired puppet version:
```bash
$ ./install_puppet.sh 3.6.1
```

If no puppet version is specified, the latest available version will be used.

###What this script affects

* A yum or apt repository will be added to your system. Pacman will be used on Arch.
* Puppet and facter will be installed, along with any other dependencies
* On RPM-based systems, the puppetlabs GPG key will be added
* wget may be installed if needed
* on Debian, the ca-certificates package will be installed if needed

##Limitations

This script is designed to work with RHEL, Debian, and arch-derived systems.
Other distros and OSes are not supported and will not work.

There is no warranty on this tool. It does get some degree of testing, but if
you want a tested and supported tool you should look at Puppet Enterprise. If
you encounter problems, please open an issue on the github repo.

##Credits

Many, many thanks to Luke Cyca's excellent github.com/lukecyca/travis-docker-example
work figuring out how to run Docker containers in travis-ci. Awesome work!
