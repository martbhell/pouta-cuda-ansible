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

Cool Features We Could Do
-------------------------

 - Spawn the instance with ansible
