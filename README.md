# projet-ansible


création d'users :

playbook:

vars:
    client:
        - username: client1
         domaine: client1.com
         password: vault

        - username: client2
        etc



on appelle:

user: {{item.username}}

with-item:
    {{item}}


Vault password:
Tous les mot de passe client dans password.yml