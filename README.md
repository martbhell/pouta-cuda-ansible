pouta-cuda-demo
--------------

Usage:

 - Create a hosts file and add your VM there
 - Run ansible.

<pre>
ansible-playbook -i inventory site.yml 
</pre>

ssh in and try to use the GPGPU:
<pre>
$ sudo nvidia-smi
</pre>

Or use ansible for this too:
<pre>
$ ansible -i inventory -m command -a "/usr/bin/nvidia-smi" all
</pre>

Cool Features We Could Do
-------------------------

 - Spawn the instance with ansible
