Vagrant.configure("2") do |config|
    servers = [
      {
        :hostname => "control",
        :box => "generic/ubuntu1804",
        :ip => "192.168.122.50",
        :ssh_port => '2200'
      },
      {
        :hostname => "node1",
        :box => "generic/ubuntu1804",
        :ip => "192.168.122.51",
        :ssh_port => '2201'
      },
      {
        :hostname => "node2",
        :box => "generic/ubuntu1804",
        :ip => "192.168.122.52",
        :ssh_port => '2202'
      },
      {
        :hostname => "node3",
        :box => "generic/ubuntu1804",
        :ip => "192.168.122.53",
        :ssh_port => '2203'
      }
    ]
  
    servers.each do |machine|
      config.vm.define machine[:hostname] do |node|
        node.vm.box = machine[:box]
        node.vm.hostname = machine[:hostname]
        node.vm.network :private_network, ip: machine[:ip]
        node.vm.network "forwarded_port", guest: 22, host: machine[:ssh_port], id: "ssh"
        
        node.vm.provider :libvirt do |libvirt|
          libvirt.memory = 512
          libvirt.cpus = 1
        end
      end
    end
  end