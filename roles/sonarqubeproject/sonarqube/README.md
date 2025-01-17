Role Name
=========

sonarqube

Requirements
------------
- Ansible 2.9+ installed on your control machine.
- A target Linux server with apt package manager (e.g., Ubuntu or Debian).
- Sudo privileges on the target server.
- At least 2GB RAM for SonarQube and 3GB RAM for production-grade performance.



Role Variables
--------------
- The role uses the following configurable variables:
Variable	       Default Value	                                                                       Description
sonarqube_download_url	https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.9.1.69595.zip	URL for downloading SonarQube.
sonarqube_user	        sonarqube	                                                                        User under which SonarQube will run.
sonarqube_install_dir	/opt/sonarqube	                                                                        Directory where SonarQube will be installed.
sonarqube_port	        9000	                                                                                Port for accessing the SonarQube web interface.
sonarqube_host	        0.0.0.0	                                                                                Host to bind SonarQube (accessible from anywhere).




Usage Instructions
------------

1- Clone the Repository Clone the GitHub repository to your control machine:

   - git clone https://github.com/mennamoustafagaber/myprojects.git
   - cd myprojects/roles/sonarqubeproject

2- Define a Playbook Create a playbook (e.g., sonarqube-playbook.yml) to include this role:

    - hosts: all
      become: yes
      roles:
        - sonarqube


3- Run the Playbook Execute the playbook against your target servers:
   - ansible-playbook -i inventory sonarqube-playbook.yml


4- Access SonarQube
    After successful setup, open a browser and navigate to:
    http://<your-server-ip>:9000
     Default credentials:
      Username: admin
      Password: admin




