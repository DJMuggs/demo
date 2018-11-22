# This is a docker demo using Vagrant and libvirt

Clone the repo and enter the challenge directory.

Run the playbook to prepare you hosts for this demo
`ansible-playbook -i inventory/hosts playbook.yml -K`

Run `vagrant up` and you should be set.

Capture the IP address from the vagrant deployment.
Use a browser to go to http://<captured ip> for the loadbalancing test
Use a browser to go to http://<captured ip>:70 for the haproxy stats
