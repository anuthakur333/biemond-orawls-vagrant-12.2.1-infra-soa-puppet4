# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "soa2admin2" , primary: true do |soa2admin2|

    soa2admin2.vm.box = "centos-7-1611-x86_64"
    soa2admin2.vm.box_url = "https://dl.dropboxusercontent.com/s/e7o5lvlpletkp2i/centos-7-1611-x86_64.box"

    soa2admin2.vm.provider :vmware_fusion do |v, override|
      override.vm.box = "centos-7-1611-x86_64-vmware"
      override.vm.box_url = "https://dl.dropboxusercontent.com/s/6hqh2ntbiyu3srt/centos-7-1611-x86_64-vmware.box"
    end

    soa2admin2.vm.hostname = "soa2admin2.example.com"
    soa2admin2.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777","fmode=777"]
    soa2admin2.vm.synced_folder "/Users/edwinbiemond/software", "/software"

    soa2admin2.vm.network :private_network, ip: "10.10.10.21"

    soa2admin2.vm.provider :vmware_fusion do |vb|
      vb.vmx["numvcpus"] = "2"
      vb.vmx["memsize"] = "3548"
    end

    soa2admin2.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "2548"]
      vb.customize ["modifyvm", :id, "--name"  , "soa2admin2"]
      vb.customize ["modifyvm", :id, "--cpus"  , 2]
    end

    soa2admin2.vm.provision :shell, :inline => "ln -sf /vagrant/puppet/hiera.yaml /etc/puppetlabs/code/hiera.yaml;rm -rf /etc/puppetlabs/code/modules;ln -sf /vagrant/puppet/environments/development/modules /etc/puppetlabs/code/modules"


    soa2admin2.vm.provision :puppet do |puppet|

      puppet.environment_path     = "puppet/environments"
      puppet.environment          = "development"

      puppet.manifests_path       = "puppet/environments/development/manifests"
      puppet.manifest_file        = "site.pp"

      puppet.options           = [
                                  '--verbose',
                                  '--report',
                                  '--trace',
                                  # '--debug',
#                                  '--parser future',
                                  '--strict_variables',
                                  '--hiera_config /vagrant/puppet/hiera.yaml'
                                 ]
      puppet.facter = {
        "environment"     => "development",
        "vm_type"         => "vagrant",
      }

    end

  end

  config.vm.define "mft1admin" , primary: true do |mft1admin|

    mft1admin.vm.box = "centos-7-1611-x86_64"
    mft1admin.vm.box_url = "https://dl.dropboxusercontent.com/s/e7o5lvlpletkp2i/centos-7-1611-x86_64.box"

    mft1admin.vm.provider :vmware_fusion do |v, override|
      override.vm.box = "centos-7-1611-x86_64-vmware"
      override.vm.box_url = "https://dl.dropboxusercontent.com/s/6hqh2ntbiyu3srt/centos-7-1611-x86_64-vmware.box"
    end

    mft1admin.vm.hostname = "mft1admin.example.com"
    mft1admin.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777","fmode=777"]
    mft1admin.vm.synced_folder "/Users/edwinbiemond/software", "/software"

    mft1admin.vm.network :private_network, ip: "10.10.10.71"

    mft1admin.vm.provider :vmware_fusion do |vb|
      vb.vmx["numvcpus"] = "2"
      vb.vmx["memsize"] = "3548"
    end

    mft1admin.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", "2548"]
      vb.customize ["modifyvm", :id, "--name"  , "mft1admin"]
      vb.customize ["modifyvm", :id, "--cpus"  , 2]
    end

    mft1admin.vm.provision :shell, :inline => "ln -sf /vagrant/puppet/hiera.yaml /etc/puppetlabs/code/hiera.yaml;rm -rf /etc/puppetlabs/code/modules;ln -sf /vagrant/puppet/environments/development/modules /etc/puppetlabs/code/modules"

    mft1admin.vm.provision :puppet do |puppet|

      puppet.environment_path     = "puppet/environments"
      puppet.environment          = "development"

      puppet.manifests_path       = "puppet/environments/development/manifests"
      puppet.manifest_file        = "site.pp"

      puppet.options           = [
                                  '--verbose',
                                  '--report',
                                  '--trace',
                                  # '--debug',
#                                  '--parser future',
                                  '--strict_variables',
                                  '--hiera_config /vagrant/puppet/hiera.yaml'
                                 ]
      puppet.facter = {
        "environment"     => "development",
        "vm_type"         => "vagrant",
      }


    end

  end

  config.vm.define "soadb" , primary: true do |soadb|

    soadb.vm.box = "centos-7-1611-x86_64"
    soadb.vm.box_url = "https://dl.dropboxusercontent.com/s/e7o5lvlpletkp2i/centos-7-1611-x86_64.box"

    soadb.vm.provider :vmware_fusion do |v, override|
      override.vm.box = "centos-7-1611-x86_64-vmware"
      override.vm.box_url = "https://dl.dropboxusercontent.com/s/6hqh2ntbiyu3srt/centos-7-1611-x86_64-vmware.box"
    end

    soadb.vm.hostname = "soadb.example.com"
    soadb.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777","fmode=777"]
    soadb.vm.synced_folder "/Users/edwinbiemond/software", "/software"

    soadb.vm.network :private_network, ip: "10.10.10.5"

    soadb.vm.provider :vmware_fusion do |vb|
      vb.vmx["numvcpus"] = "2"
      vb.vmx["memsize"] = "2548"
    end

    soadb.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm"     , :id, "--memory", "2548"]
      vb.customize ["modifyvm"     , :id, "--name"  , "soadb"]
      vb.customize ["modifyvm"     , :id, "--cpus"  , 2]
    end

    soadb.vm.provision :shell, :inline => "ln -sf /vagrant/puppet/hiera.yaml /etc/puppetlabs/code/hiera.yaml;rm -rf /etc/puppetlabs/code/modules;ln -sf /vagrant/puppet/environments/development/modules /etc/puppetlabs/code/modules"

    soadb.vm.provision :puppet do |puppet|

      puppet.environment_path     = "puppet/environments"
      puppet.environment          = "development"

      puppet.manifests_path       = "puppet/environments/development/manifests"
      puppet.manifest_file        = "db.pp"

      puppet.options           = [
                                  '--verbose',
                                  '--report',
                                  '--trace',
                                  # '--debug',
#                                  '--parser future',
                                  '--strict_variables',
                                  '--hiera_config /vagrant/puppet/hiera.yaml'
                                 ]
      puppet.facter = {
        "environment"     => "development",
        "vm_type"         => "vagrant",
      }

    end

  end

end
