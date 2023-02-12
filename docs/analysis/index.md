# Performance Analysis

- Check CPU Freq
    ```
    cat /proc/cpuinfo | grep MHz
    ```
- install cpufreq uitl
    ```
    sudo apt install cpufrequtils
    ```

- setting cpu freq
    ```
    sudo vim /etc/default/cpufrequtils

    ENABLE="true"
    GOVERNOR="powersave"
    MAX_SPEED=2.61GHz
    MIN_SPEED=2.60GHz
    ```
