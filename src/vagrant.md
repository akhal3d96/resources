# Vagrant

## Create cluster of multiple nodes

```ruby

Vagrant.configure("2") do |config|
  
  # Specif the number of nodes
  num_of_nodes = 3
  
  (0..(num_of_nodes - 1)).each do |node|

	# Append a number to the node name
    node_name = "vm-#{node + 1}"

    config.vm.define node_name do |node|
		
		# VM Settings such as network and disks

      node.vm.provider "virtualbox" do |vb|
        # Vendor specific settings such as VirtualBox GUI 
      end
    end
  end
end
```

## References
[Vagrant Documentation](https://www.vagrantup.com/docs)