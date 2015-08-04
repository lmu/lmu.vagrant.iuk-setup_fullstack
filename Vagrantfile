# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "canonical/trusty64"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"

  config.vm.define "appdb1" do |appdb1|
    appdb1.vm.provider "virtualbox" do |vb|
      vb.name = "APPDB1"
      vb.memory = 4096
      vb.cpus = 4
    end
    appdb1.vm.network :private_network, ip: "192.168.1.11"
  end

  config.vm.define "appdb2", autostart: false do |appdb2|
    appdb2.vm.provider "virtualbox" do |vb|
      vb.name = "APPDB2"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
    end
    appdb2.vm.network :private_network, ip: "192.168.1.12"
  end

  config.vm.define "app3" do |app3|
    app3.vm.provider "virtualbox" do |vb|
      vb.name = "APP3"
      vb.memory = 4096
      vb.cpus = 4
    end
    app3.vm.network :private_network, ip: "192.168.1.15"
  end

  config.vm.define "app4", autostart: false do |app4|
    app4.vm.provider "virtualbox" do |vb|
      vb.name = "APP4"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
    end
    app4.vm.network :private_network, ip: "192.168.1.16"
  end

  config.vm.define "search3" do |search3|
    search3.vm.provider "virtualbox" do |vb|
      vb.name = "Search3"
      vb.memory = 4096
      vb.cpus = 4
    end
    search3.vm.network :private_network, ip: "192.168.1.21"
  end

  config.vm.define "search4", autostart: false do |search4|
    search4.vm.provider "virtualbox" do |vb|
      vb.name = "Search4"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
    end
    search4.vm.network :private_network, ip: "192.168.1.22"
  end

  config.vm.define "webproxy1" do |webproxy1|
      webproxy1.vm.provider "virtualbox" do |vb|
      vb.name = "WebProxy1"
      vb.memory = 4096
      vb.cpus = 4
    end
    webproxy1.vm.network :private_network, ip: "192.168.1.31"
  end

  config.vm.define "webproxy2", autostart: false do |webproxy2|
    webproxy2.vm.provider "virtualbox" do |vb|
      vb.name = "WebProxy2"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
    end
    webproxy2.vm.network :private_network, ip: "192.168.1.32"
  end

  config.vm.define "sentry" do |sentry|
    sentry.vm.provider "virtualbox" do |vb|
      vb.name = "Sentry1"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
    end
    sentry.vm.network :private_network, ip: "192.168.1.90"
  end

  config.vm.define "piwik" do |piwik|
    piwik.vm.provider "virtualbox" do |vb|
      vb.name = "Piwik"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
    end
    piwik.vm.network :private_network, ip: "192.168.1.49"
  end

  config.vm.define "special" do |special|
    special.vm.provider "virtualbox" do |vb|
      vb.name = "Special"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
    end
    special.vm.network :private_network, ip: "192.168.1.5"

    # Provisioning only on last maschine but for all:
    config.vm.provision "ansible" do |ansible|
      ansible.groups = {
        "appdbs" => ["appdb1", "appdb2"],
        "apps" => ["app3", "app4"],
        "searchs" => ["search3", "search4"],
        "webproxies" => ["webproxy1", "webproxy2"],
        "sentrys" => ["sentry"],
        "piwik-dbs" => ["piwik"],
        "piwik-masters" => ["piwik"],
        "piwik-workers" => ["piwik"],
        "serverraum-ludwig27" => ["appdb1", "app3", "search3", "webproxy1", "special", "piwik"],
        "serverraum-martius4" => ["appdb2", "app4", "search4", "webproxy2"]
      }
      ansible.verbose = ""
      ansible.limit = "all"
      #ansible.playbook = "lmu.ansible.playbooks/base-preseed.yml"
      ansible.playbook = "lmu.ansible.playbooks/iuk_fullstack.yml"
      ansible.ask_vault_pass = true
    end
  end

end
