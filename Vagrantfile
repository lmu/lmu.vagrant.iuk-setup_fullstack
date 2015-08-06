# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

# Special Settings for this Vagrant Environment
USE_PUBLIC_NETWORK = false
#USE_PUBLIC_NETWORK = true
PRIVATE_NETWORK_BASE = "192.168.1"
#PRIVATE_NETWORK_BASE = PRIVATE_NETWORK_BASE + ""
PUBLIC_NETWORK_BASE = "137.193.211"
#PUBLIC_NETWORK_BASE = "192.168.2"
AUTOSTART_SECONDARY = false
#AUTOSTART_SECONDARY = true
AUTOSTART_INFRASTRUKTURE = false
#AUTOSTART_INFRASTRUKTURE = true

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "canonical/trusty64"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"

  # Disbale default synced_folder as ther is no need for this.
  config.vm.synced_folder ".", "/vagrant", disabled: true 

  config.vm.define "appdb1.verwaltung.uni-muenchen.de" do |appdb1|
    appdb1.vm.provider "virtualbox" do |vb|
      vb.name = "APPDB1"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Plone"
                   ]
    end
    appdb1.vm.network :private_network, ip: PRIVATE_NETWORK_BASE + ".210"
    if USE_PUBLIC_NETWORK
      appdb1.vm.network :public_network, ip: PUBLIC_NETWORK_BASE + ".210"
    end
  end

  config.vm.define "appdb2.verwaltung.uni-muenchen.de", autostart: AUTOSTART_SECONDARY do |appdb2|
    appdb2.vm.provider "virtualbox" do |vb|
      vb.name = "APPDB2"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Plone"
                   ]
    end
    appdb2.vm.network :private_network, ip: PRIVATE_NETWORK_BASE + ".211"
    if USE_PUBLIC_NETWORK
      appdb2.vm.network :public_network, ip: PUBLIC_NETWORK_BASE + ".211"
    end
  end

  config.vm.define "app3.verwaltung.uni-muenchen.de" do |app3|
    app3.vm.provider "virtualbox" do |vb|
      vb.name = "APP3"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Plone"
                   ]
    end
    app3.vm.network :private_network, ip: PRIVATE_NETWORK_BASE + ".215"
    if USE_PUBLIC_NETWORK
      app3.vm.network :public_network, ip: PUBLIC_NETWORK_BASE + ".215"
    end
  end

  config.vm.define "app4.verwaltung.uni-muenchen.de", autostart: AUTOSTART_SECONDARY do |app4|
    app4.vm.provider "virtualbox" do |vb|
      vb.name = "APP4"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Plone"
                   ]
    end
    app4.vm.network :private_network, ip: PRIVATE_NETWORK_BASE + ".216"
    if USE_PUBLIC_NETWORK
      app4.vm.network :public_network, ip: PUBLIC_NETWORK_BASE + ".216"
    end
  end

  config.vm.define "search3.verwaltung.uni-muenchen.de" do |search3|
    search3.vm.provider "virtualbox" do |vb|
      vb.name = "Search3"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Solr"
                   ]
    end
    search3.vm.network :private_network, ip: PRIVATE_NETWORK_BASE + ".208"
    if USE_PUBLIC_NETWORK
      search3.vm.network :public_network, ip: PUBLIC_NETWORK_BASE + ".208"
    end
  end

  config.vm.define "search4.verwaltung.uni-muenchen.de", autostart: AUTOSTART_SECONDARY do |search4|
    search4.vm.provider "virtualbox" do |vb|
      vb.name = "Search4"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Solr"
                   ]
    end
    search4.vm.network :private_network, ip: PRIVATE_NETWORK_BASE + ".209"
    if USE_PUBLIC_NETWORK
      search4.vm.network :public_network, ip: PUBLIC_NETWORK_BASE + ".209"
    end
  end

  config.vm.define "webproxy1.verwaltung.uni-muenchen.de" do |webproxy1|
      webproxy1.vm.provider "virtualbox" do |vb|
      vb.name = "WebProxy1"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/WebProxies"
                   ]
    end
    webproxy1.vm.network :private_network, ip: PRIVATE_NETWORK_BASE + ".205"
    if USE_PUBLIC_NETWORK
      webproxy1.vm.network :public_network, ip: PUBLIC_NETWORK_BASE + ".205"
    end
  end

  config.vm.define "webproxy2.verwaltung.uni-muenchen.de", autostart: AUTOSTART_SECONDARY do |webproxy2|
    webproxy2.vm.provider "virtualbox" do |vb|
      vb.name = "WebProxy2"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/WebProxies"
                   ]
    end
    webproxy2.vm.network :private_network, ip: PRIVATE_NETWORK_BASE + ".206"
    if USE_PUBLIC_NETWORK
      webproxy2.vm.network :public_network, ip: PUBLIC_NETWORK_BASE + ".206"
    end
  end

  config.vm.define "sentry1.verwaltung.uni-muenchen.de", autostart: AUTOSTART_INFRASTRUKTURE do |sentry|
    sentry.vm.provider "virtualbox" do |vb|
      vb.name = "Sentry1"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Sentry"
                   ]
    end
    sentry.vm.network :private_network, ip: PRIVATE_NETWORK_BASE + ".190"
    if USE_PUBLIC_NETWORK
      sentry.vm.network :public_network, ip: PUBLIC_NETWORK_BASE + ".190"
    end
  end

  config.vm.define "piwik1.verwaltung.uni-muenchen.de", autostart: AUTOSTART_INFRASTRUKTURE do |node|
    node.vm.provider "virtualbox" do |vb|
      vb.name = "Piwik1"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU/Piwik"
                   ]
    end
    node.vm.network :private_network, ip: PRIVATE_NETWORK_BASE + ".195"
    if USE_PUBLIC_NETWORK
      node.vm.network :public_network, ip: PUBLIC_NETWORK_BASE + ".195"
    end
  end

  config.vm.define "special.verwaltung.uni-muenchen.de", autostart: AUTOSTART_INFRASTRUKTURE do |node|
    node.vm.provider "virtualbox" do |vb|
      vb.name = "Special"
      vb.memory = 4096
      vb.cpus = 4
      vb.customize ["modifyvm", :id,
                    "--cpuexecutioncap", "50",
                    "--groups", "/Vagrant/LMU"
                   ]
    end
    node.vm.network :private_network, ip: PRIVATE_NETWORK_BASE + ".200"
    if USE_PUBLIC_NETWORK
      node.vm.network :public_network, ip: PUBLIC_NETWORK_BASE + ".200"
    end

    if ENV['OS'] != "Windows_NT" # Windows don't support ansible, 
      # Provisioning only on last maschine but for all:
      config.vm.provision "ansible" do |ansible|
        ansible.groups = {
          "appdbs" => ["appdb1.verwaltung.uni-muenchen.de", "appdb2.verwaltung.uni-muenchen.de"],
          "apps" => ["app3.verwaltung.uni-muenchen.de", "app4.verwaltung.uni-muenchen.de"],
          "searchs" => ["search3.verwaltung.uni-muenchen.de", "search4.verwaltung.uni-muenchen.de"],
          "webproxies" => ["webproxy1.verwaltung.uni-muenchen.de", "webproxy2.verwaltung.uni-muenchen.de"],
          "sentrys" => ["sentry1.verwaltung.uni-muenchen.de"],
          "piwik-dbs" => ["piwik1.verwaltung.uni-muenchen.de"],
          "piwik-masters" => ["piwik1.verwaltung.uni-muenchen.de"],
          "piwik-workers" => ["piwik1.verwaltung.uni-muenchen.de"],
          "infrastruktur:children" => [],
          "serverraum-ludwig27" => ["appdb1", "app3", "search3", "webproxy1", "special", "piwik"],
          "serverraum-martius4" => ["appdb2", "app4", "search4", "webproxy2"],
          "DMZ-CMS" => ["plone"],
          "DMZ-Webproxies:children" => ["webproxies"],
          "DMZ-Analytics" => ["piwik"],
          "DMZ-Infrastruktur" => ["infrastruktur"],
        }
        #ansible.verbose = "vvvv"
        ansible.verbose = ""
        ansible.limit = "all"
        #ansible.playbook = "lmu.ansible.playbooks/base-preseed.yml"
        ansible.playbook = "lmu.ansible.playbooks/iuk_fullstack.yml"
        #ansible.ask_vault_pass = true
      end
    end
  end

end
