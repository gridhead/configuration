# Installing Docker on CentOS host

1. Clone the repo to your local storage and make the `installing-docker-on-centos-host` directory your current working directory.
2. Make changes to `prepbook.yml` according to your preferences to reflect the changes in `hostaddr`, `username` and `servlist` variable.
3. Once done, execute the following command to populate the primary playbook and inventory file.
    ```
    ansible-playbook prepbook.yml -vvv
    ```
4. Two new files would be generated as a result, so execute the following command to actually start installing .
    ```
    ansible-playbook -i register.ini instplay.yml -vvv
    ```
