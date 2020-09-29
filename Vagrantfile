Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"

  provisioner = Vagrant::Util::Platform.windows? ? :ansible_local : :ansible

  config.vm.define "ub20" do |host|
    host.vm.network :private_network, ip: "192.168.33.13"
    host.vm.hostname = "ub20"
    host.vm.provision provisioner do |ansible|
      ansible.playbook = "playbook.yml"
    end
  end

end