# ansible-learn
How to deploy to remote server with **Ubuntu 16.04** using Ansible 2.x

I suppose you are using OSX (El Capitan) as host OS

## Install Ansible

First install "pip" - Python package manager:

`$ sudo easy_install pip`

And then install Ansible with:

`$ sudo pip install ansible`

Install Python PassLib library to use password hash:

`$ sudo pip install passlib`

If you have different OS, please look at http://docs.ansible.com/ansible/intro_installation.html

## Init remote server

Generate ssh keys:

`$ ssh-keygen -b 4096`

Create password hash from *plaintextpassword* for deploy user on remote server:

`$ python -c "from passlib.hash import sha512_crypt; print sha512_crypt.encrypt('plaintextpassword')"`

Edit **initialize_basic_user.yml** with *NORMAL_USER_NAME*, *password* and *authorized_key*

Run init playbook (will ask for root password on remote server):

`$ ansible-playbook -i hosts --ask-pass -u root initialize_basic_user.yml`

## Pitfalls

To get rid of **AttributeError: 'EntryPoint' object has no attribute 'resolve'** use:

`$ pip install cryptography==1.2.1`
