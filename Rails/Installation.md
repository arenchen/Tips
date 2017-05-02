# Setup Ruby On Rails on Ubuntu 16.04
```shell
sudo apt-get update -y
sudo apt-get install build-essential libssl-dev libreadline-dev zlib1g-dev
```
## Install rbenv
```shell
git clone https://github.com/rbenv/rbenv.git ~/.rbenv

# build
cd ~/.rbenv && src/configure && make -C src

# Add ~/.rbenv/bin to your $PATH for access to the rbenv command-line utility.
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile

# initialize rbenv
~/.rbenv/bin/rbenv init
eval "$(rbenv init -)"
```

## Install ruby-build as an rbenv plugin
```shell
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
```

## Installing Ruby versions
```shell
source ~/.bash_profile

# list all available versions:
rbenv install -l

# install a Ruby version:
rbenv install 2.4.1

# set to default
rbenv global 2.4.1
```

## Install Rails
```shell
gem install bundler
gem install rails
```
