# projet-ansible

Start :

ansible-playbook system.yml -i host.yml

- share ssh key
- Add user ansible with sudo right to execute playbook
- update package in server
- Installation rsyslog and enable this
- Add server in syslog server to centralize logs
- Dynamic host file

Database setup : (Olivier)

- To install MySQL service on both DB servers, execute : 
ansible-playbook -i hosts.yml installsql.yml -kK
- To setup Master and Slave servers, execute :
ansible-playbook -i hosts.yml setupmaster.yml -kK
ansible-playbook -i hosts.yml setupslave.yml -kK
- To create a MySQL user, execute :
ansible-playbook -i hosts.yml createsqluser.yml -kK
- To create a Database using the dump.sql file, execute : 
ansible-playbook -i hosts.yml createdb.yml -kK
- To get the File and Position value (needed for Replication setup), execute : 
ansible-playbook -i hosts.yml setupreplication.yml -kK


Syslog Setup:

1 - Launch ansible-playbook -i hosts.yml syslog.yml -kK

2 - To configure a server to communicate with syslog, execute : ansible-playbook -i hosts.yml system.yml -kK


User Client :

To create an user :
  
  - Enter information in WordPress_LAMP/vars/user_vars.yml
      - username :
      - domain :
      - password : "{{user}}"
      - home:
   
   - For add a password, go to : WordPress_LAMP/Vault/password.yml
        - execute : ansible-vault edit password.yml
        - add line : {{user}}: password
        
    - execute ansible-playbook webserver/user.yml -i host.yml --ask-vault-pass
    
  
  
  HeartBeat:
  
  Change ip and interface in :
    - templates/hacf.j2
    - haressources.j2
  
  to execute HeartBeat : ansible-playbook heartbeat.yml -i host.yml
  
  
  Index of default page Apache in templates/index.html.j2
  
  

