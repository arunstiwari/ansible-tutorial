---
- hosts: webservers
  remote_user: ubuntu
  #become: yes
  
  tasks:

  - name: Ensure group "admin" exists
    group:
      name: admin
      state: present
   
  - name: Ensure User "admin" exists
    user:
      name: admin
      state: present
      group: admin        

  - file: 
      state: directory
      path: /tmp/nginx
      owner: admin
      group: admin
      mode: 0755    


-------------
2. Removing the directory nginx from the tmp folder

- file: 
      state: absent
      path: /tmp/nginx
      owner: admin
      group: admin
      mode: 0755 

------------------
3. 
- name: Remove User "admin" if it exists
    user:
      name: admin
      state: absent
      group: admin 

 - name: Ensure group "admin" exists
    group:
      name: admin
      state: absent 