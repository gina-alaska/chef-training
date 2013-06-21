GINA/IARC Chef Training
==================

### Install Ruby 1.9.3 and RubyGems

#### Linux

ubuntu users:
```bash
sudo apt-get install zlib1g-dev openssl libopenssl-ruby1.9.1 libssl-dev libruby1.9.1 libreadline-dev git-core
```
fedora users:
```
yum groupinstall -y "Development Tools" && yum install -y readline-devel zlib-devel ncurses-devel openssl-devel
```

```bash
git clone http://github.com/sstephenson/rbenv ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
exec $SHELL -l
git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
rbenv install 1.9.3-p392
rbenv global 1.9.3-p392
gem install bundler
rbenv rehash
```
#### Mac
Prereq: Install xcode and then install the Command Line Tools from the download tab of the xcode preferences
```bash
ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
brew install ruby-build
brew install rbenv
rbenv install 1.9.3-p392
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
exec $SHELL -l
rbenv global 1.9.3-p392
gem install bundler
rbenv rehash
``` 

### Clone this cookbook
```bash
git clone http://github.com/gina-alaska/chef-training.git
cd chef-training
bundle install
rbenv rehash
```

### Install VirtualBox
```bash
https://www.virtualbox.org/wiki/Downloads
```

### Install Vagrant
```bash
http://downloads.vagrantup.com/tags/v1.2.2
```

### Install Vagrant plugins
```bash
vagrant plugin install vagrant-berkshelf
```

### Install the berkshelf config
```bash
cp config.json ~/.berkshelf/config.json
```

### Create a test cookbook and run it
```bash
berks cookbook test-cookbook --chef-minitest
cd test-cookbook
vagrant up
```

If everything worked out you should get some green text after few minutes that looks like:
```bash
Finished tests in 0.013892s, 215.9469 tests/s, 143.9646 assertions/s.

1 tests, 1 assertions, 0 failures, 0 errors, 0 skips

[2013-05-09T19:19:53+00:00] INFO: Report handlers complete
```


## Keep learning
[GINA Chef Wiki](https://github.com/gina-alaska/chef-training/wiki)
