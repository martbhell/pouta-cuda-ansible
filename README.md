pouta-cuda-demo
--------------

The spawn a VM playbook is based on https://github.com/CSCfi/pouta-ansible-demo - more usage instructions are available there.

Usage:

 - source the openrc file
 - Run ansible.

<pre>
$ source project-openrc.sh
$ ansible-playbook -u cloud-user site.yml
</pre>

Now you'll need to assign a public IP manually if the auto_ip didn't assign one..

ssh in and try to use the GPGPU:
<pre>
$ sudo nvidia-smi
</pre>

Or use ansible for this too:
<pre>
$ ansible -i inventory -m command -a "/usr/bin/nvidia-smi" all
</pre>

FAQ:
-----

The nvidia-kmod DKMS needs to match the running kernel or nothing works. To verify that DKMS is configured **incorrectly** run:

<pre>
$ dkms status
nvidia, 375.51: added
</pre>

Fix this by:
 - yum update
 - reboot
 - dkms autoinstall

Good looking DKMS status looks like this:
<pre>
$ dkms status
nvidia, 375.51, 3.10.0-514.26.2.el7.x86_64, x86_64: installed
</pre>

Cool things we could do:
----------

For when spawning many GPUs - don't waste floating IPs and use a bastion host

http://docs.ansible.com/ansible/latest/intro_dynamic_inventory.html#example-openstack-external-inventory-script
