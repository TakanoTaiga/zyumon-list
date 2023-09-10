# ROS2
- colcon build
    ```shell
    colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=Release --cargo-args --release
    ```
- colcon options
    ```shell
    --packages-up-to
    ```
    
    ```shell
    --symlink-install
    ```
    
    ```shell
    --merge-install
    ```
- rosdep
    ```shell
    rosdep install -y --from-paths src --ignore-src --rosdistro $ROS_DISTRO
    ```
 
- Add Serial Permission

    ```shell
    sudo gpasswd --add $USER dialout
    reboot
    ```
