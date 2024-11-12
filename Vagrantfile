
Vagrant.configure("2") do |javaApp|
    javaApp.vm.box = "ubuntu/bionic64"
    javaApp.vm.hostname = "java-app.box"
    javaApp.vm.network "private_network", ip: "192.168.57.10"
  
    javaApp.vm.provider "virtualbox" do |vb|
      vb.name = "JavaAppVM"
      vb.memory = 1024
      vb.cpus = 2
    end

    javaApp.vm.provision "shell", inline: <<-SCRIPT
      export APP_ENV=staging
      echo "We use $APP_ENV environment"
    SCRIPT

    javaApp.vm.provision "shell", inline: <<-SCRIPT
      sudo apt-get update -y && sudo apt-get upgrade -y
    SCRIPT

    install_deps = <<-SCRIPT
      sudo apt-get update -y
      sudo apt-get install -y openjdk-17-jdk
      echo "Java 17 installed successfully!"
    SCRIPT

    javaApp.vm.provision "shell", inline: install_deps

    javaApp.vm.synced_folder "./javavm-data", "/vagrant_data", type: "rsync"
  
  end
  