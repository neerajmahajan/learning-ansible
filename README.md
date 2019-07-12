# learning-ansible

##### YAML

* Key: Value
* Array/List
* Dictionary/Map


```
Fruits:
    - Banana:
        Calories: 105
        Fat:  0.4g
        Carbs: 27 g
    - Grape:
        Calories: 62
        Fat:  0.3g
        Carbs: 16 g 

```


#### Ansible Inventory

* information about the system/hosts ansible with manage
* Linux - SSH
* Windows - Powersheell Remoting
* default path /etc/ansible/hosts
* inventory file
    * list of servers
    ```
    # Sample Inventory File
    
    Server1.company.com
    Server2.company.com
    
    [mail]    
    Server3.company.com
    Server4.company.com
    
    ```
   * In above example, mail is a group of servers.
   * Inventory Parameters
        * ansible_connection
             * ssh
             * winrm
             * localhost
        * ansible_port
             * 22
             * 5986
        * ansible_user
             * root
             * administrator
        * ansible_ssh_pass
             * Password
    * Ansible Vault
        * For storing passwords
     ```
     #Sample Inventory File
     
     web ansible_host=Server1.company.com ansible_connection=ssh ansible_user=root
     db ansible_host=Server2.company.com ansible_connection=winrm ansible_user=admin
     mail ansible_host=Server3.company.com ansible_connection=ssh ansible_ssh_pass=P@hhhh
     web2 ansible_host=Server4.company.com ansible_connection=winrm
     
     localhost ansible_connection=localhost
     ```
     * In above example web,db,mail,web2 are just alias names.
     
     
  ##### Ansible Playbooks
  
  * Playbook is written in an YAML.
  * Play defines a set ot activities (task) to be run on hosts.
  * Task is an action to be performed on the host
       * It can be executing a command
       * Run a script
       * Install a package
       * Shutdown/Restart
  ```
   #Simple Ansible Playbook1.yml
   -
      name: Play 1
      hosts: localhost
      tasks:
          - name: Execute command `date`
            command: date
            
          - name: Execute script on server
            script: test_scripts.sh
            
          - name: Install httpd service
            yum:
               name: httpd
               state: present
          
          - name: Start web server
            service:
                name: http
                state: started
    
     ```
    
             
