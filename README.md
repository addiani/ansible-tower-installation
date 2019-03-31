# ansible-tower-installation
yum install -y epel-release 
yum install -y yum-utils device-mapper-persistent-data lvm2 ansible git python-devel python-pip python-docker-py vim-enhanced 
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo 
 yum install docker-ce -y 
systemctl start docker 
systemctl enable docker 
 git clone https://github.com/ansible/awx.git 
cd awx  
git clone https://github.com/ansible/awx-logos.git 
cd installer/ 

vim inventory 

postgres_data_dir=/var/lib/pgdocker 
awx_official=true 
project_data_dir=/var/lib/awx/projects 

ansible-playbook -i inventory install.yml -vv 

docker container ls
