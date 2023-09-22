0x0A. Configuration management
Requirements
Puppet manifests must pass puppet-lint version 2.1.1 without any errors
Puppet manifests must run without error
Puppet manifests first line must be a comment explaining what the Puppet manifest is about
Puppet manifests files must end with the extension .pp
File Description
Mandatory
0-create_a_file.pp - Using Puppet, create a file in /tmp

Requirements:
File path is /tmp/school
File permission is 0744
File owner is www-data
File group is www-data
File contains I love Puppet
root@6712bef7a528:~# puppet-lint --version
puppet-lint 2.5.2
root@6712bef7a528:~# puppet-lint 0-create_a_file.pp
root@6712bef7a528:~# 
root@6712bef7a528:~# puppet apply 0-create_a_file.pp
Notice: Compiled catalog for 6712bef7a528.ec2.internal in environment production in 0.04 seconds
Notice: /Stage[main]/Main/File[school]/ensure: defined content as '{md5}f1b70c2a42a98d82224986a612400db9'
Notice: Finished catalog run in 0.03 seconds
root@6712bef7a528:~#
root@6712bef7a528:~# ls -l /tmp/school
-rwxr--r-- 1 www-data www-data 13 Mar 19 23:12 /tmp/school
root@6712bef7a528:~# cat /tmp/school
I love Puppetroot@6712bef7a528:~#
1-install_a_package.pp - Using Puppet, install flask from pip3

Requirements:
Install flask
Version must be 2.1.0
root@9665f0a47391:/# puppet apply 1-install_a_package.pp
Notice: Compiled catalog for 9665f0a47391 in environment production in 0.14 seconds
Notice: /Stage[main]/Main/Package[Flask]/ensure: created
Notice: Applied catalog in 0.20 seconds
root@9665f0a47391:/# flask --version
Python 3.8.10
Flask 2.1.0
Werkzeug 2.1.1
2-execute_a_command.pp - create a manifest that kills a process named killmenow

Requirements:
Must use the exec Puppet resource
Must use pkill
