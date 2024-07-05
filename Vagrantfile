Vagrant.configure("2") do |config|
      config.vm.define "control" do |control|
        control.vm.box = "generic/ubuntu1804"
        control.vm.hostname = "control"
        control.vm.network :private_network, ip: "192.168.122.50"
        control.vm.network "forwarded_port", guest: 22, host: 2200, id: "ssh"
        control.vm.synced_folder "../data", "/home/vagrant/data"
        control.vm.provision "file", source: "./copiedfile.txt", destination: "/home/vagrant/copiedfile.txt"
        control.vm.provider :libvirt do |libvirt|
          libvirt.memory = 512
          libvirt.cpus = 1
        end
      end
    
      config.vm.define "node1" do |node1|
        node1.vm.box = "generic/ubuntu1804"
        node1.vm.hostname = "node1"
        node1.vm.network :private_network, ip: "192.168.122.51"
        node1.vm.network "forwarded_port", guest: 22, host: 2201, id: "ssh"
        node1.vm.synced_folder "../data", "/home/vagrant/data"
        node1.vm.provision "file", source: "./copiedfile.txt", destination: "/home/vagrant/copiedfile.txt"
        node1.vm.provider :libvirt do |libvirt|
          libvirt.memory = 512
          libvirt.cpus = 1
        end
      end
    
      config.vm.define "node2" do |node2|
        node2.vm.box = "generic/ubuntu1804"
        node2.vm.hostname = "node2"
        node2.vm.network :private_network, ip: "192.168.122.52"
        node2.vm.network "forwarded_port", guest: 22, host: 2202, id: "ssh"
        node2.vm.synced_folder "../data", "/home/vagrant/data"
        node2.vm.provision "file", source: "./copiedfile.txt", destination: "/home/vagrant/copiedfile.txt"
        node2.vm.provider :libvirt do |libvirt|
          libvirt.memory = 512
          libvirt.cpus = 1
        end
      end

      config.vm.define "node3" do |node3|
        node3.vm.box = "generic/ubuntu1804"
        node3.vm.hostname = "node3"
        node3.vm.network :private_network, ip: "192.168.56.53"
        node3.vm.network "forwarded_port", guest: 22, host: 2203, id: "ssh"
        node3.vm.synced_folder "../data", "/home/vagrant/data"
        node3.vm.provision "file", source: "./copiedfile.txt", destination: "/home/vagrant/copiedfile.txt"
        node3.vm.provider :libvirt do |libvirt|
          libvirt.memory = 512
          libvirt.cpus = 1
        end
      end
    end