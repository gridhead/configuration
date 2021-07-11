# Pulling Docker images on CentOS host

1. Clone the repo to your local storage and make the `pulling-docker-images-on-centos-host` directory your current working directory.
2. Make changes to `prepbook.yml` according to your preferences to reflect the changes in `hostaddr`, `username`, `imejlist` and `servlist` variables.
3. Once done, execute the following command to populate the primary playbook and inventory file.
    ```
    ansible-playbook prepbook.yml -vvv
    ```
4. Fetch the `community.docker` collection from Ansible Galaxy by executing the following command.
    ```
    ansible-galaxy collection install community.docker
    ```
5. Two new files would be generated as a result, so execute the following command to actually start pulling images from DockerHub.
    ```
    ansible-playbook -i register.ini pullplay.yml -vvv
    ```