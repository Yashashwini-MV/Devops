# 🚀 Jenkins + Maven + Ansible CI/CD Flow

## Steps:

```bash
java --version
sudo apt update
sudo apt install jenkins -y
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
# 5. Go into your Maven project
cd <your-maven-folder-name>
ls

# 6. Open pom.xml to customize project if needed
nano pom.xml

# 7. Build project and generate JAR
mvn package

# 8. Locate the generated JAR file
ls target/*.jar
readlink -f target/*.jar
# 9. Create your deployment playbook
nano deployyart.yml
---

- name: Deploy artifact built by jenkins
  hosts: localhost
  become: true
  tasks:
    - name: copy JAR to deployment folder
      copy:
       src: path which we get in redlink
       dest: /opt/deploy/maven folder.jar
       ansible-plyabook deployyart.yml --ask-become-pass

Ansible Configuration (7th Step)

# 10. Create a new user
sudo adduser username

# 11. Add user to sudo group
sudo usermod -aG sudo username

# 12. Switch to the new user
sudo su - veer

# 13. Install Ansible
sudo apt update && sudo apt install ansible

# 14. Verify Ansible
ansible --version

# 15. Create inventory directory and file
sudo mkdir -p /etc/ansible
sudo nano /etc/ansible/hosts
localhost ansible_connection=local
# 16. Test Ansible connection
ansible all -m ping
---
- name: basic hello world
  hosts: all
  tasks:
   - name:print hello world
     debug:
       msg: "hello world"


 ansible-playbook playbook.yml

