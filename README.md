# ansible-learn
How to deploy to remote server using ansible

I suppose you are using OSX (El Capitan) as host OS

## Install Ansible

First install "pip" - Python package manager:

`$ sudo easy_install pip`

And then install Ansible with:

`$ sudo pip install ansible`

Install Python PassLib library to use password hash:

`$ sudo pip install passlib`

If you have different OS, please look at http://docs.ansible.com/ansible/intro_installation.html

## Pitfalls

To get rid of **AttributeError: 'EntryPoint' object has no attribute 'resolve'** use:

`$ pip install cryptography==1.2.1`
