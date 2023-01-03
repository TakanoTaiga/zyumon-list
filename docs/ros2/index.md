# ROS2
- colcon build 1
    ```shell
    colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=Release
    ```

- colcon build 2
    ```shell
    colcon build --symlink-install
    ```

- colcon build 3
    ```shell
    colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=Release --packages-up-to pkg
    ```

- rosdep
    ```shell
    rosdep install -y --from-paths src --ignore-src --rosdistro $ROS_DISTRO
    ```
 