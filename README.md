Exercise 1:

ansible-galaxy collection install infra.ee_utilities:3.1.2 containers.podman:1.10.3 community.general:7.3.0

ansible-playbook -i inventory.yml -l builder playbooks/build_ee.yml


Exercise 2:

podman login --tls-verify=false hub-student1.LAB.demoredhat.com

podman pull --tls-verify=false hub-student1.LAB.demoredhat.com/config_as_code:latest

ansible-navigator run playbooks/hub_config.yml --eei hub-student1.LAB.demoredhat.com/config_as_code -i inventory.yml -l automationhub --pa='--tls-verify=false' -m stdout


Exercise 3:

git add .

git commit -am "task3"

git push origin master

ansible-navigator run playbooks/controller_config.yml --eei hub-student1.LAB.demoredhat.com/config_as_code -i inventory.yml -l automationcontroller --pa='--tls-verify=false' -m stdout