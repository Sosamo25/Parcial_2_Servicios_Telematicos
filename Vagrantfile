Vagrant.configure("2") do |config|
  if Vagrant.has_plugin? "vagrant-vbguest"
  config.vbguest.no_install = true
  config.vbguest.auto_update = false
  config.vbguest.no_remote = true
  end
  config.vm.define :firewall do |firewall|
  firewall.vm.box = "bento/centos-7"
  firewall.vm.network :private_network, ip: "192.168.50.2"
  firewall.vm.hostname = "firewall"
  firewall.vm.network :forwarded_port, guest: 80, host:5568
  firewall.vm.network "public_network", use_dhcp_assigned_default_route: true
  end
  config.vm.define :servidorFTPSeguro do |servidorFTPSeguro|
  servidorFTPSeguro.vm.box = "bento/centos-7"
  servidorFTPSeguro.vm.network :private_network, ip: "192.168.50.3"
  servidorFTPSeguro.vm.hostname = "servidorFTPSeguro"
  servidorFTPSeguro.vm.network :forwarded_port, guest: 443, host:5567
  end
  config.vm.define :dnstest do |dnstest|
    dnstest.vm.box = "bento/ubuntu-20.04"
    dnstest.vm.network :private_network, ip: "192.168.50.7"
    dnstest.vm.hostname = "dnstest"
    end
 end





 