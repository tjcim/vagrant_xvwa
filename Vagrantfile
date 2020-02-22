$msg = <<MSG
----------------------------------------------------------
The machine is up and running. Visit the application here:

  http://localhost:5005/xvwa/

URL to setup or reset database:

  http://localhost:5005/xvwa/setup/

User Account Login Information:

  admin:admin
  xvwa:xvwa
  user:vulnerable
----------------------------------------------------------
MSG

Vagrant.configure("2") do |xvwa|
  xvwa.vm.post_up_message = $msg
  xvwa.vm.box = "ubuntu/bionic64"
  xvwa.vm.network "forwarded_port", guest: 80, host: 5005
  xvwa.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible_tasks/vagrant.yml"
    ansible.compatibility_mode = "2.0"
  end
end
