#Router Vagrant

The repository sets up a [Student Robotics](http://studentrobotics.org) router. This
is a vagrant configuration that will very easily go from scratch to a vagrantbox.

##Setup

1. Install ruby 1.9.3 or greater [RVM might help](https://rvm.io/rvm/install/)
2. Install virtualbox
3. You'll need the ruby development headers. On Fedora it's `yum install
   ruby-devel libffi-devel` on debian-like (including ubuntu) it's `apt-get
   install ruby-dev libffi-dev`.
4. `gem install vagrant`
5. `git clone https://github.com/cjsoftuk/sr-router-vagrant.git && cd
   sr-router-vagrant
6. `vagrant up --provision`
7. Wait about 20 minutes
8. `vagrant ssh` to log into the box. You have passwordless sudo from the
   vagrant user to root. In case you need to know the password it's 'vagrant'


##Some details

The Vagrant basebox upon which this is based is a debian wheezy i386 install with
very little else installed on top of it apart from those needed to make it
talk to vagrant.

This always fetches the latest stuff from puppet when the box
is built, and also does a bunch of other necessary configuration.

The virtual machine is networked into your computer via NAT. Every port on
the machine is mapped to 5000 + actual port (e.g. 5080,5443,5022). This
allows you to ssh in
