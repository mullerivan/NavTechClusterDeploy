Making a NavTech on any debian server


We use Vagrant for  Testing porpuse 
And Ansible to deploy the packages and comile  anything that we need  on bouth servers

this https://docs.google.com/document/d/1zrvnVYM4KuzA1nt9ULec7xp68z7r0jNQ2wOHziQsIn4/edit#


We have the  Playbook to deploy de incoming server to check what is going on on your server check this file.

https://github.com/mullerivan/NavTechClusterDeploy/blob/master/playbooks/roles/in_server/tasks/install.yml


To test it clone the  repository and then
run:
`vagran up --provision `
that gonna wake up 2 virtual machines and provisioning them with Ansible

TODO: outgoing server playbook


to run the  playbook on a  real server just  
Edit the  host/serverhost file with your username and your ipaddress

`ssh-copy-id username@serverip`
then:

`ansible-playbook  in_server.yml -i hosts/serverhost  --ask-sudo-pass`
