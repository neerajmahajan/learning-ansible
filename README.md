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
