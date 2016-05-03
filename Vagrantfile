# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.require_plugin "vagrant-libvirt"
Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  #config.vm.box = "uvsmtid/centos-7.0-minimal"
  #config.vm.box = "/root/GIT/vagrant-libvirt/tools/fedora21.box"
  #config.vm.box = "/var/lib/libvirt/images/ubuntu-14.04-ppc64.box"
  #config.vm.box = "/root/ubuntu.14.04.box"
  #config.vm.box = "ubuntu-16.04-ppc64le"
  #config.vm.box = "rhel72-ppc6"
  #config.vm.box = "rhel72-ppc64le.new.1"
  config.vm.box = "ubuntu-15.04-ppc64le.2"
  #config.vm.box = "/root/GIT/vagrant-libvirt/tools/vm-ppc64-2.box"

config.vm.provider :libvirt do |libvirt|

    # A hypervisor name to access. Different drivers can be specified, but
    # this version of provider creates KVM machines only. Some examples of
    # drivers are kvm (qemu hardware accelerated), qemu (qemu emulated),
    # xen (Xen hypervisor), lxc (Linux Containers),
    # esx (VMware ESX), vmwarews (VMware Workstation) and more. Refer to
    # documentation for available drivers (http://libvirt.org/drivers.html).
    libvirt.driver = "qemu"

    # The name of the server, where libvirtd is running.
    # libvirt.host = "localhost"

    # If use ssh tunnel to connect to Libvirt.
    libvirt.connect_via_ssh = false

    # The username and password to access Libvirt. Password is not used when
    # connecting via ssh.
    libvirt.username = "root"
    #libvirt.password = "secret"

    # Libvirt storage pool name, where box image and instance snapshots will
    # be stored.
    libvirt.storage_pool_name = "default"

    # Set a prefix for the machines that's different than the project dir name.
    #libvirt.default_prefix = ''
  end
  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Define a Vagrant Push strategy for pushing to Atlas. Other push strategies
  # such as FTP and Heroku are also available. See the documentation at
  # https://docs.vagrantup.com/v2/push/atlas.html for more information.
  # config.push.define "atlas" do |push|
  #   push.app = "YOUR_ATLAS_USERNAME/YOUR_APPLICATION_NAME"
  # end

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   sudo apt-get update
  #   sudo apt-get install -y apache2
  # SHELL
#  config.push.define "ftp" do |push|
#   push.host = "9.47.70.201"
#   push.username = "test"
#   push.password = "passw0rd"
#   push.secure = "true"
#   push.destination = "/home/test"
#   push.dir = "/var/lib/libvirt/images/test_images"
#  end

#   config.push.define "local-exec" do |push|
#     push.inline = <<-SCRIPT
#	sync -avvp -L /var/lib/libvirt/images/test_images/*   test@9.47.70.201:/home/test/
#     SCRIPT
#   end
	config.push.define "local-exec" do |push|
  		push.script = "my-script.sh"
	end
 config.vm.provider :libvirt do |domain|
      domain.memory = "6096"
      domain.cpus = "1"
      domain.machine_type = "pseries"
      #domain.machine_type = "pseries-2.6"
      #domain.machine_type = "powernv"
      #domain.machine_type = "pseries-2.1"
      #domain.cpu_model = "POWER8"
      domain.cpu_model = "POWER7"
      domain.cpu_mode = "custom"
      domain.video_type = "none"
      domain.graphics_type = "none"
      domain.machine_arch = "ppc64"
      domain.nested = false
      domain.disk_bus = "scsi"
      #domain.kernel = "/root/powernv/zImage.epapr"
      #domain.cmd_line = "-kernel console=ttyS0"
      domain.emulator_path = "/usr/bin/qemu-system-ppc64" 
      #domain.emulator_path = "/root/qemu/qemu-2.6.0-rc3/ppc64-softmmu/qemu-system-ppc64" 
      #domain.emulator_path = "/root/powernv/qemu-pnv/bin/qemu-system-ppc64" 
   end
#  config.vm.network :private_network do |network|
#      network.dev = "virbr1"
#      netowrk.mode = "bridge"
#      netowrk.type = "bridge"
#  end
config.ssh.password = "vagrant"
end
