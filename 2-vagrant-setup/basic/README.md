1. Create a pub/private key using the command on master node. Here the user through which we login to the child node is arun and ip address of the child node is 172.16.86.129
  ssh-keygen -t rsa -C "arun@172.16.86.129"

2. Note: the above command will prompt you to specify a file name. Give the name as ubuntu.
   Two files will be created in the directory from where you are running the above command
   One is private key ubuntu and another is public key ubuntu.pub

3. Third step is to install the public key on the remote server i.e. 172.16.86.129 using the following command
   ssh-copy-id -i ubuntu.pub arun@172.16.86.129

4. This command will create the authorized_keys in the folder /home/arun/.ssh on the 172.16.86.129 server


5. Now my hosts file has one server specified.

6. Run the playbook using the following command
  ansible-playbook -i hosts playbook.yml