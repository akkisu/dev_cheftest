# lmnpt

##1. What?
PHP & Ruby & MySQL Application Development Environment image and recipe of chef.

##2. application configuration
* Vagrant + BirtualBox
* CentOS6.5
* nginx 
* unicorn
* PHP
* ruby
* MySQL

##3. How to use
###(1) install vagrant,virtualbox
###(2) install Bundler(ruby's gem management tool),chef,knife-solo,berkshelf

```bash:
#Bundlerのインストール
sudo gem install bundler

#Gemfile作成
cat <<'EOF' > Gemfile
source 'https://rubygems.org'
gem 'chef'
gem 'knife-solo'
gem 'berkshelf'
EOF
#bundleコマンドの実行
bundle install
```

###(3) vagrant up & probision

```bash:
VAGRANT_LOG=info vagrant up --provision >&vagrant.log
```
