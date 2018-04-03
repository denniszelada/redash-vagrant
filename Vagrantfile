# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure('2') do |config|
  # FIXME: When upgrading to a future version of Ubuntu check if the workaround
  # near the top of bootstrap.sh is still needed. If not, please delete it.
  config.vm.box      = 'ubuntu/artful64' # 17.10
  config.vm.hostname = 'redash-box'

  config.vm.network :forwarded_port, guest: 80, host: 80
  config.vm.network "private_network", ip: "10.0.0.10"

  config.vm.provision :shell, path: 'bootstrap.sh', keep_color: true

  config.vm.provider 'virtualbox' do |v|
    v.memory = ENV.fetch('REDASH_BOX_RAM', 2048).to_i
    v.cpus   = ENV.fetch('REDASH_BOX_CPUS', 2).to_i
  end
end
