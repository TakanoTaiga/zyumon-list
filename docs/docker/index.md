# Docker

- arm64 Ubuntu
    ```shell
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
