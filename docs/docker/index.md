# Docker

- without sudo
    ```
    sudo usermod -aG docker $USER && newgrp docker
    ```
- restart docker
    ```
    sudo systemctl daemon-reload && sudo systemctl restart docker
    ```

- arm64 Ubuntu
    ```
    docker run -it --name test arm64v8/ubuntu:focal
    ```

- Attach new shell
    ```
    docker exec -it CONTAINER bash
    ```
- Launch Isaac ROS
    ```
    cd ~/workspaces/isaac_ros-dev/src/isaac_ros_common && ./scripts/run_dev.sh
    ```