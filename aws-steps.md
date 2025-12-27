## steps to create new environment on aws EC2

    1. create new EC2 instance
        - create a .pem key and place it in .ssh/
    2. open terminal
    3. connect to remote service
    ```
    ssh -i ~/.ssh/razer.pem ubuntu@ipaddress
    ```
    or edit config file and add host
    ```
    nano .ssh/config
    
    example:
    Host mlops
        HostName ipaddress
        user ubuntu
        idenitityfile c:/Users/.../.ssh/razer.pem
        StrictHostKeyChecking no

    ssh mlops --> to connect remote service
    ```

    4. install anaconda
    ```
    wget <url from anaconda for latest version>
    bash <anaconda.sh>
    ```

    5. install docker
    ```
    sudo apt install docker.io
    ```

    6. install docker-compose
    create directory
    ```
    mkdir dir
    cd dir
    ```
    install docker-compose
    ```
    search for docker-compose github
    open github page -> releases -> copy required docker-compose address
    ```
    wget <link> -O docker-compose --> download the file
    chmod +x docker-compose --> executable file
    cd ..
    - edit bashrc to make 'dir' accessible from any location
    nano .bashrc
    add a line at last -> export PATH="${HOME}/dir/:${PATH}"
    - save it and exit
    - execute the file
    source .bashrc
    - to check docker-compose
    which docker-compose
    - to check docker
    docker run hello-world
    - to run docker without sudo
    ```
    sudo groupadd docker
    sudo usermod -aG docker $USER
    ```
    - to add github repo
    ```
    git clone <url>
    ```
    - to connect vs code 
    install remote .ssh extension in local machine vs code
    




    
