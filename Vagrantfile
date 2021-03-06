Vagrant.configure("2") do |config|
    # INPUT PAYLOAD
    payload_file=File.expand_path('./env.yaml')
    payload=YAML.load_file(payload_file)['vcenter']

    # PLUGINS
    config.vagrant.plugins = payload['plugins']

    config.vm.box = 'dummy'
    config.vm.box_url = './example_box/dummy.box'

    config.vm.synced_folder ".", "/vagrant", disabled: true
    config.ssh.username = payload['vm']['user']
    config.ssh.password = payload['vm']['password']

    config.vm.provider :vsphere do |vsphere|
      vsphere.host = payload['host']
      vsphere.compute_resource_name = payload['compute_resource_name']
      vsphere.resource_pool_name = payload['resource_pool_name']
      vsphere.template_name = payload['template_name']
      vsphere.name = payload['guest_name']
      vsphere.user = payload['user']
      vsphere.password = payload['password']
      vsphere.insecure = true
    end

    config.vm.provision "ansible" do |ansible|
      ansible.config_file          = 'ansible.cfg'
      ansible.extra_vars           = payload['ansible']['extra_vars']
      ansible.playbook             = "./install.yaml"
      ansible.limit                = "all"
      ansible.tags                 = payload['ansible']['tags']
    end
end