#Vagrant.configure("2") do |config|
#  config.vm.box = "aeciopires/ubuntu-18.04-64-docker"
#  config.vm.box_version = "1.0.0"
#end

servers=[
  {
    :hostname => "manager1",
    :ip => "192.168.100.10",
    :ram => 1024,
    :cpu => 1
  },
  {
    :hostname => "manager2",
    :ip => "192.168.100.11",
    :ram => 1024,
    :cpu => 1
  },
  {
    :hostname => "node1",
    :ip => "192.168.100.20",
    :ram => 1024,
    :cpu => 1
  },
  {
    :hostname => "node2",
    :ip => "192.168.100.21",
    :ram => 1024,
    :cpu => 1
  },
  {
    :hostname => "node3",
    :ip => "192.168.100.22",
    :ram => 1024,
    :cpu => 1
  }
]

Vagrant.configure(2) do |config|
    servers.each do |machine|
        config.vm.define machine[:hostname] do |node|
            node.vm.box = "aeciopires/ubuntu-18.04-64-docker"
            node.vm.hostname = machine[:hostname]
            node.vm.network "private_network", ip: machine[:ip]
            node.vm.provider "virtualbox" do |vb|
                vb.customize ["modifyvm", :id, "--memory", machine[:ram]]
            end
        end
    end
end
