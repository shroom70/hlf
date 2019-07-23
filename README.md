# hlf

* Vagrant로 설치 (ubuntu 1604)
<pre>
$ vagrant box add ubuntu1604 https://cloud-images.ubuntu.com/xenial/current/xenial-server-cloudimg-amd64-vagrant.box
$ mkdir ~/works/vagrant/ubuntu1604
$ cd ~/works/vagrant/ubuntu1604
$ vagrant init ubuntu1604
$ vi Vagrantfile
  (15 line) config.vm.box = "ubuntu1604"
  (35 line) config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.provider
  vb.memory -> 4096
$ vagrant up
$ sudo timedtectl set-timezone Asia/Seoul
</pre>
