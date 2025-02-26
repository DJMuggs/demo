# This is a docker demo using Vagrant and libvirt

The demo is based on a Fedora 28 installation, will also work @ CentOS 7.

!!! Fedora 29 seems a bit unstable at the moment with Vagrant, so don't use it. !!!

Clone the repo and enter the demo directory.

Run the playbook to prepare you hosts for this demo.

Add the username you want to have access to libvirt to allow ```vagrant up```

```ansible-playbook -i inventory/hosts playbook.yml -K -e user=$username```

Run ```vagrant up``` and you should be set.

Now 2 docker images are build and deployed on the vagrant host.
Node.js image that will show the docker container hostname
Haproxy image used for loadbalancing of the 2 Node.js container instances.

Capture the IP address from the vagrant deployment.

Use a browser to go to http://$captured_ip for the loadbalancing test

Use a browser to go to http://$captured_ip:70 for the haproxy stats

```mermaid
  graph TD;
      A-->B;
      A-->C;
      B-->D;
      C-->D;
```
