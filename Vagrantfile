Vagrant.configure("2") do |config|

  # name the VMs
  config.vm.define "opencloud-opensuse-tumbleweed" do |node|

    # which image to use
    node.vm.box = "opensuse/Tumbleweed.x86_64"

    # sizing of the VMs
    node.vm.provider "libvirt" do |lv|
      lv.random_hostname = true
      lv.memory = 4096
      lv.cpus = 2
    end

    # set the hostname
    node.vm.hostname = "opencloud-opensuse-tumbleweed"

    # disable the shared folder
    node.vm.synced_folder ".", "/vagrant", disabled: true

    # Ansible
    node.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.limit = "all"
      ansible.playbook = "ansible/playbook-vagrant.yml"
    end # node.vm.provision

  end # config.vm.define servers

end # Vagrant.configure
