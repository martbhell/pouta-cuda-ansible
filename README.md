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
