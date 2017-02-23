# For InfluxDB installation on one server
Vagrant.configure("2") do |config|

  # set timezone
  if Vagrant.has_plugin?("vagrant-timezone")
    config.timezone.value = "EST"
  end

  (1..1).each do |i|
    config.vm.define "nodejs0#{i}" do |node|
       node.vm.hostname = "nodejs0#{i}"
       node.vm.box = "centos/7"
       node.vm.network "private_network", ip: "10.10.0.12#{i}"
       node.vm.provider "virtualbox" do |v|
         v.memory = 4096
       end
       node.ssh.private_key_path = "/home/vmuser/.ssh/github-zzinfotech2012"
    end
  end

  config.vm.provision "file", source: "/home/vmuser/.ssh/github-zzinfotech2012.pub", destination: "~/.ssh/authorized_keys"

end

