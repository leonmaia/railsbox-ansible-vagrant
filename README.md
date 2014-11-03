# railsbox-cookbook

Configures a development environment for Ruby on Rails development. It will have the following main components:

- RVM (user_installs)
- Oh-My-Zsh
- MySQL
- PostgreSQL
- MongoDB
- Elasticsearch
- Redis 2
- Node.js
- Bower


## Vagrant Installation
First you'll need chef-dk, so download it already at (https://downloads.getchef.com/chef-dk/) and run the installation instructions on-site.

Run ```chef verify``` so it creates the ~/.chefdk folder, after this put those lines to your $PATH:

If you don't want to use rvm or rbenv on your local machine, here's the code to install ruby 2.1.2 on Ubuntu:
```
sudo apt-get -y update
apt-get -y install build-essential zlib1g-dev libssl-dev libreadline6-dev libyaml-dev
cd /tmp
wget http://ftp.ruby-lang.org/pub/ruby/2.1/ruby-2.1.2.tar.gz 
tar -xvzf ruby-2.1.2.tar.gz
cd ruby-2.1.2/
./configure --prefix=/usr/local
make
sudo make install
```
If you are running Ubuntu, check if you have NFS installed on your system:
```
dpkg -l | grep nfs-kernel-server
```
If not run this:
```
apt-get install nfs-kernel-server
```

*Remember to put these first two lines before the rbenv/rvm load on your zshrc if you are using any of them*
```
"/opt/chefdk/bin"
"$HOME/.chefdk/gem/ruby/2.1.0/bin"

"VAGRANT_SYNCED_FOLDER=~/Projects"
```

```
sudo gem install berkshelf
vagrant plugin install vagrant-berkshelf
vagrant plugin install vagrant-omnibus

berks install
ssh-add
vagrant up --provision
```

## License and Authors
Author:: Leon Maia (hi@leonmaia.com)

*This is a modified version of the railsbox (https://github.com/akitaonrails/vagrant-railsbox) repository by Fabio Akita (boss@akitaonrails.com)*
