# install_jenkins

Ansible role to install and configure Jenkins on Linux (Ubuntu/Debian).

## Role Variables

### Default Variables (`defaults/main.yml`)
- `jenkins_version`: Version of Jenkins to install (default: 2.401.3)
- `java_package`: Java package to install (default: openjdk-11-jdk)
- `jenkins_repo_key_url`: URL for Jenkins repository key
- `jenkins_repo_url`: URL for Jenkins repository
- `jenkins_port`: Port for Jenkins (default: 8080)
- `firewall_enabled`: Whether to enable the firewall (default: true)

### Static Variables (`vars/main.yml`)
- `jenkins_package_name`: Name of the Jenkins package
- `jenkins_service_name`: Name of the Jenkins service
- `jenkins_home`: Jenkins home directory
- `jenkins_config_file`: Jenkins configuration file

## Usage

Include the role in your playbook:

```yaml
- name: Install Jenkins
  hosts: all
  become: yes
  roles:
    - role: install_jenkins

## Run the playbook using the AWS EC2 inventory

ansible-playbook -i aws_ec2.yml tests/test.yml
