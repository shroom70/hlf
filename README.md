# hlf

* 사전 설치 프로그램
<pre>
1. Visual Studio Code (https://code.visualstudio.com/)
2. VirtualBox (https://www.virtualbox.org/)
3. Vagrant (https://www.vagrantup.com/)
</pre>

* Vagrant로 설치 (ubuntu 1604)
<pre>
$ vagrant plugin install vagrant-vbguest 
$ vagrant plugin install vagrant-disksize 
$ vagrant box add ubuntu1604 https://cloud-images.ubuntu.com/xenial/current/xenial-server-cloudimg-amd64-vagrant.box
$ mkdir ~/works/vagrant/ubuntu1604
$ cd ~/works/vagrant/ubuntu1604
$ vagrant init ubuntu1604
$ vi Vagrantfile
  (15 line) config.vm.box = "ubuntu1604"
  (16 line) config.disksize.size = '40GB'
  (36 line) config.vm.network "private_network", ip: "192.168.33.10"
  (53 line) config.vm.provider
  (58 line) vb.memory = 4096
  (or)
  (add) vb.customize ["modifyvm", :id, "--cpus", 2]
  (add) vb.customize ["modifyvm", :id, "--memory", 4096]
$ vagrant up
$ sudo timedatectl set-timezone Asia/Seoul
</pre>

* VirtualBox HDD 크기 변경
<pre>
$ cd "VirtualBox VMs"/<VBox image path>
$ VBoxManage clonehd ubuntu-xenial-16.04-cloudimg.vmdk tmp-disk.vdi --format vdi
$ VBoxManage modifyhd tmp-disk.vdi --resize 40960
$ VBoxManage clonehd tmp-disk.vdi ubuntu-xenial-16.04-cloudimgX.vmdk --format vmdk

VirutalBox에서 이미지 변경
</pre>
