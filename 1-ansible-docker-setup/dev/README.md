1. Build the node image
docker build -t arunstiwari/ansible-node .

2. Create the dockerized environment 
    docker run -d -p 2222:22 --name dev -v ~/.ssh/id_rsa.pub:/home/ubuntu/.ssh/authorized_keys arunstiwari/ansible-node:latest