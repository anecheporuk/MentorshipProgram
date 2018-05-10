Vagrant.configure("2") do |config|

  config.vm.define :node1 do |node1|
    node1.vm.box = 'bento/ubuntu-16.04'
    node1.vm.network "private_network", ip: "192.168.56.100"
    node1.vm.network "forwarded_port", guest: 8080, host: 8800

    node1.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = '2.0'
      ansible.playbook = "jenkins.yml"
    end
  end

  config.vm.define :node2 do |node2|
     node2.vm.box      = 'bento/ubuntu-16.04'
     node2.vm.network "private_network", ip: "192.168.56.101"
     node2.vm.network "forwarded_port", guest: 8080, host: 8801

  node2.vm.provision "ansible" do |ansible|
     ansible.compatibility_mode = "2.0"
     ansible.playbook = "tomcat.yml"
   end
  end

  config.vm.define :node3 do |node3|
     node3.vm.box      = 'bento/ubuntu-16.04'
     node3.vm.network "private_network", ip: "192.168.56.102"
     node3.vm.network "forwarded_port", guest: 8080, host: 8802

  node3.vm.provision "ansible" do |ansible|
     ansible.compatibility_mode = "2.0"
     ansible.playbook = "gitlab.yml"
   end
  end

  config.vm.define :node4 do |node4|
    node4.vm.box      = 'centos/7'
    node4.vm.network "private_network", ip: "192.168.56.103"
    node4.vm.network "forwarded_port", guest: 8080, host: 8803

  node4.vm.provision "ansible" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "artifactory.yml"
  end
 end
end
