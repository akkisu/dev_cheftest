# lmnpr

##1. What?
PHP & Ruby & MySQL Application Development Environment image and recipe of chef.

##2. application configuration
* Vagrant + BirtualBox
* CentOS6.5
* nginx 
* PHP
* ruby
* MySQL

##3. How to use
###(1) install vagrant,virtualbox
###(2) install Bundler(ruby's gem management tool),chef,knife-solo,berkshelf

```bash:
#Bundlerのインストール
sudo gem install bundler
#bundleコマンドの実行
bundle install
```

###(3) vagrant up & probision

```bash:
bundle exec berks vendor ./cookbooks
VAGRANT_LOG=info vagrant up --provision >&vagrant.log
```
