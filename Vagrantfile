Vagrant.configure(2) do |config|
	config.vm.box = "ubuntu/bionic64"
	config.vm.hostname = "ubuntu"
	config.vm.provider :virtualbox do |vb|
    		vb.memory = "1024"
    		vb.cpus = 2
  	end
  	config.vm.provider :docker do |docker, override|
    		override.vm.box = nil
    		docker.image = "rofrano/vagrant-provider:ubuntu"
    		docker.remains_running = true
    		docker.has_ssh = true
    		docker.privileged = true
    		docker.volumes = ["/sys/fs/cgroup:/sys/fs/cgroup:ro"]
  	end
      	config.vm.provision "shell", path: "scripts/install.sh"
end
