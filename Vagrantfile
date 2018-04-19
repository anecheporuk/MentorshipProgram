Vagrant.configure("2") do |config|

  config.vm.define :node1 do |node1|
    node1.vm.box = 'bento/ubuntu-16.04'
    node1.vm.network "private_network", ip: "192.168.56.100"

    node1.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = '2.0'
      ansible.playbook = "jenkins.yml"
    end
  end

  config.vm.define :node2 do |node2|
     node2.vm.box      = 'bento/ubuntu-16.04'
     node2.vm.network "private_network", ip: "192.168.56.101"
     node2.vm.network "forwarded_port", guest: 8080, host: 8080

  node2.vm.provision "ansible" do |ansible|
     ansible.compatibility_mode = "2.0"
     ansible.playbook = "tomcat.yml"
   end
  end
end
