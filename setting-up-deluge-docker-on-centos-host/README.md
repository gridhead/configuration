# Setting up Deluge Docker on CentOS host

> Reference : https://hub.docker.com/r/linuxserver/deluge/

1. Clone the repo to your local storage and make the `setting-up-deluge-docker-on-centos-host` directory your current working directory.
2. Make changes to `prepbook.yml` according to your preferences to reflect the changes in `hostaddr`, `username`, `servlist`, `lxsvdlug_conf`, `lxsvdlug_data`, `lxsvdlug_hostname`, `lxsvdlug_webp`, `lxsvdlug_rpct`, `lxsvdlug_rpcu`, `lxsvdlug_timezone` and `lxsvdlug_loglevel` variables.
3. Once done, execute the following command to populate the primary playbook and inventory file.
    ```
    ansible-playbook prepbook.yml -vvv
    ```
4. Fetch the `community.docker` collection from Ansible Galaxy by executing the following command.
    ```
    ansible-galaxy collection install community.docker
    ```
5. Two new files would be generated as a result, so execute the following command to actually start setting up Deluge Docker.
    ```
    ansible-playbook -i register.ini trapplay.yml -vvv
    ```
6. Once the container is configured and started, open up `http://<ansible_host>:<lxsvdlug_webp>/` using a web browser of your choice on a device connected to the same network as that of the server.
7. Log in using the following credentials and you would be soon asked to change the administrator password.
    ```
    Username: admin
    Password: deluge
    ```
