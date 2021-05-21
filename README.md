1. spin up one server to serve as ansible-host
2. install ansible on ansible-host
3. nano /etc/ansible/hosts 
 
Paste this inside the hosts and change ansible_user to the users on each host machine

[hadoop]
10.243.87.248   ansible_connection=ssh ansible_user=ubuntu
10.243.87.66    ansible_connection=ssh ansible_user=ubuntu
10.243.87.219   ansible_connection=ssh ansible_user=ubuntu

[namenode]
10.243.87.219   ansible_connection=ssh ansible_user=ubuntu

[datanodes]
10.243.87.248   ansible_connection=ssh ansible_user=ubuntu
10.243.87.66    ansible_connection=ssh ansible_user=ubuntu


5. Go to the group_vars folder and change the ips and make sure it corresponds with the above
6. Unfortunately you need to ssh-copy-id from namenode to each datanode N:B will be automated later
7. This will set the system up for us to install hadoop N:B Automation ongoing . I will notify you when done