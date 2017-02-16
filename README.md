Making a NavTech on any debian server


We use ''vagrant'' for testing porpuses. 
Ansible is been used to deploy the packages and compile  anything needed for both servers.


Use this guide as reference:  https://docs.google.com/document/d/1zrvnVYM4KuzA1nt9ULec7xp68z7r0jNQ2wOHziQsIn4/edit#


We have the  Playbook to deploy the incoming server. In order to check what is going on on your server check this file.

https://github.com/mullerivan/NavTechClusterDeploy/blob/master/playbooks/roles/in_server/tasks/install.yml


To test it, clone the  repository and then
run:
`vagrant up --provision `
tis will wake up 2 virtual machines and provisioning them with Ansible

In order run the  playbook on a  real server just  
Edit the  host/serverhost file with your username and your ipaddress

`ssh-copy-id username@serverip`
then:

`ansible-playbook  in_server.yml -i hosts/serverhost  --ask-sudo-pass`




If you like this you can buy me a beer :)
navcoin:NQvnXv1HUQPzUx7oHe5MEWv71NX8A8SsTT
=======
Donations always welcome!

NAV Coin: NQvnXv1HUQPzUx7oHe5MEWv71NX8A8SsTT

#Soon: Outgoing Server Playbook

