# projet-ansible

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

