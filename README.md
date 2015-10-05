# Basic Vagrant VM for [FAF](https://github.com/FAForever)

Prerequisites
* VirtualBox: https://www.virtualbox.org/ 
* Vagrant: https://www.vagrantup.com/

# Installation

1. Clone this Repository
2. Open Shell and navigate to this repository
3. Check if `Vagrantfile` exists
4. Execute `vagrant up`
5. Login to your vm with `vagrant ssh`

Attention: On Window you have normally no ssh client in your path. Use [cygwin](https://www.cygwin.com/) 
the [bash from git](https://git-scm.com/downloads) or add another ssh client to the Window Path variable.

# Notes

* The main folder on the host is shared in the guest under `/faf` and `/vagrant`
* Port `80`, `3306`, `2000`, `3000`, `4000`, `5000`, `6000`, `7000` are forwared to the vm and must be open
