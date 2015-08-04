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
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Plone"
                   ]
    end
    appdb1.vm.network :private_network, ip: "192.168.1.11"
    if ENV['OS'] == "Windows_NT"
      appdb1.vm.network :public_network, ip: "137.193.211.203"
    end
  end

  config.vm.define "appdb2", autostart: false do |appdb2|
    appdb2.vm.provider "virtualbox" do |vb|
      vb.name = "APPDB2"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Plone"
                   ]
    end
    appdb2.vm.network :private_network, ip: "192.168.1.12"
    if ENV['OS'] == "Windows_NT"
      appdb2.vm.network :public_network, ip: "137.193.211.204"
    end
  end

  config.vm.define "app3" do |app3|
    app3.vm.provider "virtualbox" do |vb|
      vb.name = "APP3"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Plone"
                   ]
    end
    app3.vm.network :private_network, ip: "192.168.1.15"
    if ENV['OS'] == "Windows_NT"
      app3.vm.network :public_network, ip: "137.193.211.205"
    end
  end

  config.vm.define "app4", autostart: false do |app4|
    app4.vm.provider "virtualbox" do |vb|
      vb.name = "APP4"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Plone"
                   ]
    end
    app4.vm.network :private_network, ip: "192.168.1.16"
    if ENV['OS'] == "Windows_NT"
      app4.vm.network :public_network, ip: "137.193.211.206"
    end
  end

  config.vm.define "search3" do |search3|
    search3.vm.provider "virtualbox" do |vb|
      vb.name = "Search3"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Solr"
                   ]
    end
    search3.vm.network :private_network, ip: "192.168.1.21"
    if ENV['OS'] == "Windows_NT"
      search3.vm.network :public_network, ip: "137.193.211.208"
    end
  end

  config.vm.define "search4", autostart: false do |search4|
    search4.vm.provider "virtualbox" do |vb|
      vb.name = "Search4"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Solr"
                   ]
    end
    search4.vm.network :private_network, ip: "192.168.1.22"
    if ENV['OS'] == "Windows_NT"
      search4.vm.network :public_network, ip: "137.193.211.209"
    end
  end

  config.vm.define "webproxy1" do |webproxy1|
      webproxy1.vm.provider "virtualbox" do |vb|
      vb.name = "WebProxy1"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/WebProxies"
                   ]
    end
    webproxy1.vm.network :private_network, ip: "192.168.1.31"
    if ENV['OS'] == "Windows_NT"
      webproxy1.vm.network :public_network, ip: "137.193.211.201"
    end
  end

  config.vm.define "webproxy2", autostart: false do |webproxy2|
    webproxy2.vm.provider "virtualbox" do |vb|
      vb.name = "WebProxy2"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/WebProxies"
                   ]
    end
    webproxy2.vm.network :private_network, ip: "192.168.1.32"
    if ENV['OS'] == "Windows_NT"
      webproxy2.vm.network :public_network, ip: "137.193.211.202"
    end
  end

  config.vm.define "sentry" do |sentry|
    sentry.vm.provider "virtualbox" do |vb|
      vb.name = "Sentry1"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Sentry"
                   ]
    end
    sentry.vm.network :private_network, ip: "192.168.1.90"
    if ENV['OS'] == "Windows_NT"
      sentry.vm.network :public_network, ip: "137.193.211.218"
    end
  end

  config.vm.define "piwik" do |piwik|
    piwik.vm.provider "virtualbox" do |vb|
      vb.name = "Piwik"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Piwik"
                   ]
    end
    piwik.vm.network :private_network, ip: "192.168.1.49"
    if ENV['OS'] == "Windows_NT"
      piwik.vm.network :public_network, ip: "137.193.211.219"
    end
  end

  config.vm.define "special" do |special|
    special.vm.provider "virtualbox" do |vb|
      vb.name = "Special"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU"
                   ]
    end
    special.vm.network :private_network, ip: "192.168.1.5"
    if ENV['OS'] == "Windows_NT"
      special.vm.network :public_network, ip: "137.193.211.200"
    end

    if ENV['OS'] == "Windows_NT"
      config.vm.provision "shell",
        inline: "echo Windows Host"
    else
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

end
