## steps to install docker in linux machine

## Part 1: Preparing the Security Keys
    ```
    sudo apt-get update: Refreshes your local list of available software packages.

    sudo apt-get install ca-certificates curl: Installs curl (to download files) and ca-certificates (to ensure secure connections).

    sudo install -m 0755 -d /etc/apt/keyrings: Creates a specific folder to store these security keys. The -m 0755 sets the folder permissions so it’s readable by everyone but only writable by the admin.

    sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc: Downloads Docker’s official GPG public key. This is the "ID card" that verifies Docker’s software.

    sudo chmod a+r /etc/apt/keyrings/docker.asc: Makes sure the key is readable by all users on the system so the installer can use it.
    ```

### Part 2: Adding the Repository

    Now that the system has the "key," you need to tell it where the "store" (repository) is located.
    
    ```
    echo "deb [arch=$(dpkg --print-architecture) ...": This builds a long string of text that tells Linux exactly where to find the Docker files.

    arch=$(dpkg --print-architecture): Automatically detects if your computer is 64-bit (x86_64) or ARM.

    signed-by=...: Tells Linux to use the specific key you just downloaded to verify this specific repository.

    $(. /etc/os-release && echo "$VERSION_CODENAME"): Automatically detects your Ubuntu version (like "jammy" or "noble") so you get the right version of Docker.

    sudo tee /etc/apt/sources.list.d/docker.list: This takes that long string of text and writes it into a new file called docker.list. This is like adding Docker to your system’s "address book" of software sources.

    sudo apt-get update: Runs a refresh again. Now, your system will see the Docker repository and the software inside it.

    exact commands:
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

    sudo apt-get update
    
    ```
### 3. Install the Docker packages.
    ```
    sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

    ```

#### To run docker without sudo:
    ```
    sudo groupadd docker
    sudo usermod -aG docker $USER
    ```

#### Step 4: Run Docker
    ```
    docker run hello-world
    ```

    ```
    If you get docker: Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/create": dial unix /var/run/docker.sock: connect: permission denied. error, restart your VM instance, or run: sudo dockerd

    Note: If you get It is required that your private key files are NOT accessible by others. This private key will be ignored. error, you should change permits on the downloaded file to protect your private key:

    chmod 400 name-of-your-private-key-file.pem

    ```
    

