# Setting up Plex Docker on CentOS host

> Reference : https://hub.docker.com/r/linuxserver/plex

1. Clone the repo to your local storage and make the `setting-up-plex-docker-on-centos-host` directory your current working directory.
2. Make changes to `prepbook.yml` according to your preferences to reflect the changes in `hostaddr`, `username`, `servlist`, `lxsvplex_libr`, `lxsvplex_tvsr`, `lxsvplex_movs`, `lxsvplex_hostname`, `lxsvplex_webp`, `lxsvplex_tcp1`, `lxsvplex_tcp2`, `lxsvplex_tcp3`, `lxsvplex_udp1`, `lxsvplex_udp2`, `lxsvplex_udp3`, `lxsvplex_udp4`, `lxsvplex_udp5`, `lxsvplex_timezone` and `lxsvplex_authcode` variables.
3. Retrieve the `lxsvplex_authcode` by visiting https://plex.tv/claim. 
4. Once done, execute the following command to populate the primary playbook and inventory file.
    ```
    ansible-playbook prepbook.yml -vvv
    ```
5. Fetch the `community.docker` collection from Ansible Galaxy by executing the following command.
    ```
    ansible-galaxy collection install community.docker
    ```
6. Two new files would be generated as a result, so execute the following command to actually start setting up Plex Docker.
    ```
    ansible-playbook -i register.ini trapplay.yml -vvv
    ```
7. Once the containers are configured and started, open up `http://<ansible_host>:<lxsvplex_authcode>/web` (or `http://192.168.29.152:32400/web` if nothing was changed) using a web browser of your choice on a device connected to the same network as that of the server.
8. Log in using the account to get started with using Plex.
