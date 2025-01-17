Role Name and Description
=========

nexus 

This Ansible role automates the installation and configuration of Nexus Repository Manager on a Linux server. It ensures all required dependencies are installed, downloads Nexus, and sets it up as a systemd service for easy management.



Requirements
------------

- Ansible 2.9+ installed on your control machine.
- A target Linux server with apt package manager (e.g., Ubuntu or Debian).
- Sudo privileges on the target server.


Role Variables
--------------
The role uses the following variables, which can be customized in your playbooks:

Variable	       Default Value	                                                Description
nexus_download_url	https://download.sonatype.com/nexus/3/latest-unix.tar.gz	URL for the Nexus tarball.
nexus_user	        nexus	                                                        User under which Nexus will run.
nexus_install_dir	/opt/nexus	                                                Directory where Nexus will be installed.
nexus_data_dir	        /opt/sonatype-work/nexus3	                                Directory for Nexus data storage.

Usage Instructions:
------------
1- Clone the Repository Clone the GitHub repository to your control machine:
- git clone https://github.com/mennamoustafagaber/myprojects.git
- cd myprojects/roles/nexusproject/nexus

2- Define a Playbook Create a playbook (e.g., nexus-playbook.yml) to include this role:

- hosts: all
  become: yes
  roles:
    - nexus
3- Run the Playbook Execute the playbook against your target servers:
- ansible-playbook -i inventory nexus-playbook.yml


4- Access Nexus

- After the playbook runs successfully, Nexus will be available as a service.
- Open a browser and navigate to http://<your-server-ip>:8081 to access the Nexus UI.
- Default credentials:
    Username: admin
    Password: Found in /opt/sonatype-work/nexus3/admin.password.
    Systemd Service





