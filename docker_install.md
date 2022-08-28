# Docker engine installation

## Requirements 

Your Windows machine must meet the following requirements to successfully install Docker Desktop.

  - Install WSL 2.
  - Enable Hyper-V and Containers Windows features.

## Install Docker Desktop on Windows

  - Download Docker Desktop Installer.exe from : [Docker Desktop for Windows](https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe)
  - Run Docker Desktop Installer.exe file.
  - Ensure the Enable Hyper-V Windows Features or the Install required Windows components for WSL 2 option is selected on the Configuration page.
  - Follow the instructions on the installation wizard to authorize the installer and proceed with the install.
  - When the installation is successful, click Close to complete the installation process.

## Check docker installation

  - Open WSL Session of your linux distribution
  - Run the following test:
    ```sh
    docker run hello-world
    ```
  - If you have permission problems, run:
    ```sh
    sudo docker run hello-world
    ```

## Solver docker permissions

  - Open WSL Session of your linux distribution
  - Run the following Commands
    - Create the docker group if it does not exist
      ```sh
      sudo groupadd docker
      ```
    - Add your user to the docker group.
      ```sh
      sudo usermod -aG docker $USER
      ```
    - change the user's group ID of the session.
      ```sh
      newgrp docker
      ```
    - Check if docker can be run without root
      ```sh
      docker run hello-world
      ```
    - Reboot if still got error
      ```sh
      reboot
      ```

# Docker Compose installation

  - Open WSL Session of your linux distribution
  - Run this command to download the current stable release of Docker Compose:
    ```sh
    sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
    ```
    To install a different version of Compose, substitute 1.29.2 with the version of Compose you want to use.
  - Apply executable permissions to the binary:
    ```sh
    sudo chmod +x /usr/local/bin/docker-compose
    ```
  - Create a symbolic link
    ```sh
    sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
    ```
  - test the installation
    ```sh
    docker-compose --version
    ```

# References

- [Docker engine installation guide](https://docs.docker.com/desktop/windows/install/)
- [Docker compose installation guide](https://docs.docker.com/compose/install/)