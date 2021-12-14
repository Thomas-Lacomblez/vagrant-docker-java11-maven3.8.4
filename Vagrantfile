Vagrant.configure("2") do |config|

  config.vm.provider :docker do |d|
    config.vm.synced_folder "/absolute/path/to/your/projects", "/home/vagrant/projets_Java"
    d.build_dir = "."
    d.remains_running = true
    d.has_ssh = true
    d.name = "env-jdk11-maven3.8.4"
  end
end