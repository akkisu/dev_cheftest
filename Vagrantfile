
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.hostname = "guest"
  config.vm.box = "centos6.5"
  config.vm.box_url = "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-6.5-i386_chef-provisionerless.box"
  
  config.vm.network "private_network", ip: "192.168.33.10"

  # vagrant-omnibusの有効化
  config.omnibus.chef_version = :latest
  # Chef solo の設定
  config.vm.provision :chef_solo do |chef|
    # クックブックの配置場所
    chef.cookbooks_path = ["./cookbooks","./site-cookbooks"]

    # Attributeの定義
    chef.json = {
      nginx: {
        env: ["php"]
      }
    }
    
    #適用するクックブックの定義
    chef.run_list = %w[
      recipe[yum]
      recipe[yum-epel]
      recipe[nginx]
      recipe[php-env]
      recipe[ruby-env]
    ]
  end
end