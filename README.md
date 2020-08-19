# Ansible
Ansible permite a los DevOps gestionar sus servidores, configuraciones y aplicaciones de forma sencilla, robusta y paralela
https://github.com/ansible/ansible
* Algunos comandos

  > ansible all -m user -a “name=user password-redhat”
  > ansible servers -m apt -a "name=nginx state=present"
  > ansible -m ping all
  > ansible -m ping servers
  > ansible -i /etc/ansible/hosts servers -m ping
	> ansible-playbook demo.yml --syntax-check
  > ansible-playbook demo.yml 
  > ansible-playbook -i /etc/ansible/hosts demo.yml

## Instala Ansible en tu servidor principal (bastion):
* apt-get install ansible || yum install ansible || pip install ansible
* Verifica tu archivo de configuraciones de ansible
> cat ansible.cfg
* Adiciona tu host o grupos de hosts al archivo de inventarios
> vim /etc/ansible/hosts
## Prueba el ssh
* Genera un ssh-keygen en tu servidor principal y copialo a un servidor host secundario valido
> vim .ssh/authorized_keys
* Envia una prueba desde el servidor principal, en demo.yml puedes encontrar un ejemplo basico de tareas: envio de files, instalacion e inicio de servicios

## Crea una infraestructura con Ansible y AWS
* Configura tu servidor principal, crea un usuario, crea un role y adiciona al servidor, configura una regla para permitir ssh en el inbound de securitygroups
* Ingresa en el servidor principal instala Ansible si no lo tienes
* Instala boto, boto3
* Opcional: si deseas puedes utilizar un entorno virtual para administrar boto, boto3
> pip install boto, boto3
* Puedes utilizar playbook.yml para crear VMs en AWS
* Puedes utilizar terminateplaybook.yml para terminar las VMs 

## Links de interes:
Windows: https://youtu.be/FEdXUv02Dbg
Aws: https://youtu.be/1v-5cDuDRHI
Links de documentacion:
https://docs.ansible.com/ansible/latest/modules/ec2_module.html

