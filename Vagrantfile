if not File.exists?("cookbooks")
    system "git clone git://github.com/nonameentername/cookbooks.git" 
end

Vagrant::Config.run do |config|
  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "lucid64"
  config.vm.box_url = "http://files.vagrantup.com/lucid64.box"

  # Enable provisioning with chef solo, specifying a cookbooks path (relative
  # to this Vagrantfile), and adding some recipes and/or roles.
  #
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = ["cookbooks"]
    chef.add_recipe "main"
    chef.add_recipe "android-ndk"
    chef.add_recipe "python-android"
  end
end
