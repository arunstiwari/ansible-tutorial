1. Using File module

  - file: 
      state: touch
      path: /tmp/file2
  
  - file: 
      state: absent
      path: /tmp/file2    

  - file: 
      state: touch
      path: /tmp/file2
      mode: 0644

  # touch the same file, but add/remove some permissions
  - file:
      path: /etc/foo.conf
      state: touch
      mode: "u+rw,g-wx,o-rwx"    

//Here make sure you have added become: yes as it requires elevated right
  - file: 
      state: directory
      path: /tmp/tomcat
      mode: 0755    

  - name: Ensure group "somegroup" exists
    group:
      name: tomcat
      state: present    



  https://docs.ansible.com/ansible/2.5/modules/file_module.html#file-module    