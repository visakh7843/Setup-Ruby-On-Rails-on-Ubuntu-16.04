# Setup-Ruby-On-Rails-on-Ubuntu-16.04
Setup Ruby On Rails on Ubuntu 16.04 using RVM


The first step is to install some dependencies for Ruby.

sudo apt-get update
sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-d



The installation for rvm is pretty simple:

sudo apt-get install libgdbm-dev libncurses5-dev automake libtool bison libffi-dev
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
curl -sSL https://get.rvm.io | bash -s stable
source ~/.rvm/scripts/rvm
rvm install 2.4.0
rvm use 2.4.0 --default
ruby -v

The last step is to install Bundler

gem install bundler

Installing Rails

Since Rails ships with so many dependencies these days, we're going to need to install a Javascript runtime like NodeJS. This lets you use Coffeescript and the Asset Pipeline in Rails which combines and minifies your javascript to provide a faster production environment.

To install NodeJS, we're going to add it using the official repository:

curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs

And now, without further adieu:

gem install rails -v 5.1.1

If you're using rbenv, you'll need to run the following command to make the rails executable available:

rbenv rehash

Now that you've installed Rails, you can run the rails -v command to make sure you have everything installed correctly:

rails -v
# Rails 5.1.1

If you get a different result for some reason, it means your environment may not be setup properly.
