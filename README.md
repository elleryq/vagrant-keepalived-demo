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

## Reference

* [使用 Haproxy + Keepalived 构建基于 Docker 的高可用负载均衡服务（一） - CODING 博客](https://blog.coding.net/blog/Haproxy&Keepalived)
