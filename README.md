# keepalived demo

Vagrantfile to demo keepalived.

* OS: CentOS8
* Provisioner: Ansible

There are 4 VMs:

* u3: Backend of HAProxy, I use httpd as backend.
* master/slave: HAProxy Cluster by keepalived.
* u4: Bastion for testing

After VMs are provisioned, you can ssh into u4: `vagrant ssh u4`

Then run `watch "curl -s http://192.168.60.10"`

Open another terminal, type `vagrant ssh master -c "sudo systemctl stop keepalived"`

Then see the result of first terminal.
