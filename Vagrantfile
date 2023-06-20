VAGRANT_COMMAND = ARGV[0]

Vagrant.configure("2") do |config|
  config.vm.provider :libvirt do |libvirt|
    libvirt.management_network_address = "192.168.121.0/24"
    libvirt.default_prefix = "two-router-t_"
  end
  config.vm.define "r1" do |r1|
    r1.vm.provider :libvirt do |domain|
      domain.management_network_mac = "08:4f:a9:00:00:01"
      domain.qemu_use_session = false
    end
    r1.vm.box = "cisco/csr1000v"
    r1.vm.synced_folder ".", "/vagrant", disabled: true
    r1.ssh.insert_key = false
    r1.vm.boot_timeout = 360
    r1.vm.allow_fstab_modification = false
    r1.vm.allow_hosts_modification = false
    r1.vm.guest = :freebsd

    r1.vm.provider :libvirt do |domain|
      domain.nic_adapter_count = 8
      domain.memory = 4096
      domain.cpus = 2
      domain.driver = "kvm"
    end
    r1.vm.provider :libvirt do |domain|
    end

    r1.vm.network :private_network,
                  :libvirt__tunnel_type => "udp",
                  :libvirt__tunnel_local_ip => "127.1.1.1",
                  :libvirt__tunnel_local_port => "10002",
                  :libvirt__tunnel_ip => "127.1.1.2",
                  :libvirt__tunnel_port => "10002",
                  :libvirt__iface_name => "vgif_r1_2",
                  auto_config: false
    r1.vm.network :private_network,
                  :libvirt__tunnel_type => "udp",
                  :libvirt__tunnel_local_ip => "127.1.1.1",
                  :libvirt__tunnel_local_port => "10003",
                  :libvirt__tunnel_ip => "127.1.1.3",
                  :libvirt__tunnel_port => "10003",
                  :libvirt__iface_name => "vgif_r1_3",
                  auto_config: false
  end
  config.vm.define "r2" do |r2|
    r2.vm.provider :libvirt do |domain|
      domain.management_network_mac = "08:4f:a9:00:00:02"
      domain.qemu_use_session = false
    end
    r2.vm.box = "cisco/csr1000v"
    r2.vm.synced_folder ".", "/vagrant", disabled: true
    r2.ssh.insert_key = false
    r2.vm.boot_timeout = 360
    r2.vm.allow_fstab_modification = false
    r2.vm.allow_hosts_modification = false
    r2.vm.guest = :freebsd

    r2.vm.provider :libvirt do |domain|
      domain.nic_adapter_count = 8
      domain.memory = 4096
      domain.cpus = 2
      domain.driver = "kvm"
    end
    r2.vm.provider :libvirt do |domain|
    end

    r2.vm.network :private_network,
                  :libvirt__tunnel_type => "udp",
                  :libvirt__tunnel_local_ip => "127.1.1.2",
                  :libvirt__tunnel_local_port => "10002",
                  :libvirt__tunnel_ip => "127.1.1.1",
                  :libvirt__tunnel_port => "10002",
                  :libvirt__iface_name => "vgif_r2_2",
                  auto_config: false
    r2.vm.network :private_network,
                  :libvirt__tunnel_type => "udp",
                  :libvirt__tunnel_local_ip => "127.1.1.2",
                  :libvirt__tunnel_local_port => "10003",
                  :libvirt__tunnel_ip => "127.1.1.3",
                  :libvirt__tunnel_port => "10002",
                  :libvirt__iface_name => "vgif_r2_3",
                  auto_config: false
  end
  config.vm.define "r3" do |r3|
    r3.vm.provider :libvirt do |domain|
      domain.management_network_mac = "08:4f:a9:00:00:03"
      domain.qemu_use_session = false
    end
    r3.vm.box = "cisco/csr1000v"
    r3.vm.synced_folder ".", "/vagrant", disabled: true
    r3.ssh.insert_key = false
    r3.vm.boot_timeout = 360
    r3.vm.allow_fstab_modification = false
    r3.vm.allow_hosts_modification = false
    r3.vm.guest = :freebsd

    r3.vm.provider :libvirt do |domain|
      domain.nic_adapter_count = 8
      domain.memory = 4096
      domain.cpus = 2
      domain.driver = "kvm"
    end
    r3.vm.provider :libvirt do |domain|
    end

    r3.vm.network :private_network,
                  :libvirt__tunnel_type => "udp",
                  :libvirt__tunnel_local_ip => "127.1.1.3",
                  :libvirt__tunnel_local_port => "10002",
                  :libvirt__tunnel_ip => "127.1.1.2",
                  :libvirt__tunnel_port => "10003",
                  :libvirt__iface_name => "vgif_r3_2",
                  auto_config: false
    r3.vm.network :private_network,
                  :libvirt__tunnel_type => "udp",
                  :libvirt__tunnel_local_ip => "127.1.1.3",
                  :libvirt__tunnel_local_port => "10003",
                  :libvirt__tunnel_ip => "127.1.1.1",
                  :libvirt__tunnel_port => "10003",
                  :libvirt__iface_name => "vgif_r3_3",
                  auto_config: false
  end
end
