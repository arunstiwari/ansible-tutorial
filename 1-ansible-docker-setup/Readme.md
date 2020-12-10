1. Build the Docker Image
    docker build -t arunstiwari/ansible .

2. Test the ansible playbook running inside the container by executing the following command
    docker run --rm -it -v $(pwd):/ansible/playbooks arunstiwari/ansible --version

3. To run any playbook file like site.yml from inside the container
  docker run --rm -it -v $(pwd):/ansible/playbooks arunstiwari/ansible site.yml

4. If ansible is interacting with the external machines, you will need to mount an SSH key pair for the duration of the play
    docker run --rm -it -v ~/.ssh/id_rsa:/root/.ssh/id_rsa -v ~/.ssh/id_rsa.pub:/root/.ssh/id_rsa.pub -v $(pwd):/ansible/playbooks arunstiwari/ansible playbook.yml

   Change the 
    docker run --rm -it -v ~/.ssh/id_rsa:/root/.ssh/id_rsa -v ~/.ssh/id_rsa.pub:/root/.ssh/id_rsa.pub -v $(pwd):/ansible/playbooks arunstiwari/ansible remote.yml -i inventory



5. sudo docker run -d -P --name dev arunstiwari/ubuntu-sshd:16.04
6. sudo docker port dev 22
7. ssh root@localhost -p <portnumber>
    here port number is what you got from step 6
8.