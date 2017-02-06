## Synopsis

This is a simple standalone Ansible script for building a Cuckoo Sandbox server. The following capabilities are included:

- Cuckoo Sandbox (current Git version)
- Web UI
- Yara v3.5.0
- Volatility v2.6
- Elasticsearch v2.x
- SSDeep
- Support for ESX, vSphere and KVM machinery

## Installation
This installation process has been tested against a fresh install of _ubuntu-16.04.1-server-amd64_ with the following package options:

- standard system utilities
- OpenSSH server

After the base OS install a dist-upgrade was conducted:

`apt-get update & apt-get dist-upgrade`

Now to build the Cuckoo environment:

1. Clone this repository:
`git clone https://github.com/PingTrip/Ansible_Cuckoo.git`
2. If you have any pre-configured Cuckoo files place them in the ./conf_files directory.
3. Replace the placeholders in the install command with the correct ones for your installation:

`ansible-playbook -i "HOST," -e "ansible_ssh_user=ADMIN" --ask-pass --ask-sudo-pass install_cuckoo.yml`

- **HOST** is the IP address of the server to install Cuckoo to. _Note: the comma after the HOST is not a typo. Ansible is expecting a list, so the comma is required_
- **ADMIN** is a user with sudo privileges on the server

By default, Cuckoo will be installed to /opt/cuckoo and a cuckoo user will be created. These values can be modified at the top of the script:

    cuckoo_user: 'cuckoo'
    cuckoo_dir: '/opt/cuckoo'

## Usage

Once the installation has completed run the following as the "cuckoo" user:

    cd /opt/cuckoo/web
    python manage.py runserver 0.0.0.0:8080 &
    cd ..
    ./cuckoo.py




