# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "canonical/trusty64"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
  config.vm.box_check_update = true

  config.vm.define "appdb1" do |appdb1|
    appdb1.vm.provider "virtualbox" do |vb|
      vb.name = "APPDB1"
      vb.memory = 4096
      vb.cpus = 4
    end
    appdb1.vm.network :private_network, ip: "192.168.1.11"
  end

  config.vm.define "appdb2" do |appdb2|
    appdb2.vm.provider "virtualbox" do |vb|
      vb.name = "APPDB2"
      vb.memory = 4096
      vb.cpus = 4
    end
    appdb2.vm.network :private_network, ip: "192.168.1.12"
  end

    config.vm.define "app1" do |app1|
    app1.vm.provider "virtualbox" do |vb|
      vb.name = "APP1"
      vb.memory = 4096
      vb.cpus = 4
    end
    app1.vm.network :private_network, ip: "192.168.1.15"
  end

  config.vm.define "app2" do |app2|
    app2.vm.provider "virtualbox" do |vb|
      vb.name = "APP2"
      vb.memory = 4096
      vb.cpus = 4
    end
    app2.vm.network :private_network, ip: "192.168.1.16"
  end

  config.vm.define "search1" do |search1|
    search1.vm.provider "virtualbox" do |vb|
      vb.name = "Search1"
      vb.memory = 4096
      vb.cpus = 4
    end
    search1.vm.network :private_network, ip: "192.168.1.21"
  end

  config.vm.define "search2" do |search2|
    search2.vm.provider "virtualbox" do |vb|
      vb.name = "Search2"
      vb.memory = 4096
      vb.cpus = 4
    end
    search2.vm.network :private_network, ip: "192.168.1.22"
  end

  config.vm.define "webproxy1" do |webproxy1|
      webproxy1.vm.provider "virtualbox" do |vb|
      vb.name = "WebProxy1"
      vb.memory = 4096
      vb.cpus = 4
    end
    webproxy1.vm.network :private_network, ip: "192.168.1.31"
  end

  config.vm.define "webproxy2" do |webproxy2|
    webproxy2.vm.provider "virtualbox" do |vb|
      vb.name = "WebProxy2"
      vb.memory = 4096
      vb.cpus = 4
    end
    webproxy2.vm.network :private_network, ip: "192.168.1.32"
  end

  config.vm.define "special" do |special|
    special.vm.provider "virtualbox" do |vb|
      vb.name = "Special"
      vb.memory = 4096
      vb.cpus = 4
    end
    special.vm.network :private_network, ip: "192.168.1.5"

    # Provisioning only on last maschine but for all:
    config.vm.provision "ansible" do |ansible|
      ansible.groups = {
        "appdbs" => ["appdb1", "appdb2"],
        "apps" => ["app1", "app2"],
        "searchs" => ["search1", "search2"],
        "webproxies" => ["webproxy1", "webproxy2"],
        "serverraum-ludwig27" => ["appdb1", "app1", "search1", "webproxy1", "special"],
        "serverraum-martius4" => ["appdb2", "app2", "search2", "webproxy2"]
      }
      ansible.verbose = ""
      ansible.limit = "all"
      ansible.playbook = "playbook.yml"
    end
  end

end
