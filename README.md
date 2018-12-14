# Ansible playbooks for my Fedora 28 laptops
Playbooks that bootstrap my many fedora laptops so that I can go and sip yorkshire tea while the ansible is doing all the tedious work.

### Start
Generate ssh keys:

    ssh-keygen -C $USER@$HOSTNAME
    ssh-keygen -o -a 100 -t ed25519 -C $USER@$HOSTNAME
    
Add ssh key to bitbucket and github.

Clone this repo:

    git clone https://github.com/hoto/ansible-home-fedora.git

Install ansible and dependencies:

    sudo dnf install ansible python-dnf libselinux-python

Install chrome:

    ansible-playbook chrome.yml -K

Add ssh key to github:

    https://github.com/settings/keys

Clone and setup my home:

    ansible-playbook home.yml

Add ssh key to bitbucket:

    https://bitbucket.org/account/user/hoto/ssh-keys

Install software:

    ansible-playbook software.yml -K

TODO:
- fix hstr on zsh
- clone all my github repos
- install slack using flackpack
- enable night light 
- disable animations from gnome tweaks (for speed)
- add automatic build for testing installation of the software
