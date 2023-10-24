# Check CPU status

- Check CPU Freq
    ```
    cat /proc/cpuinfo | grep MHz
    ```

# cpufrequtils
- install cpufrequitl
    ```
    sudo apt install cpufrequtils
    ```
- perf setting 
   ```
   sudo sh -c 'echo -1 > /proc/sys/kernel/perf_event_paranoid'
   sudo sh -c 'echo 0 > /proc/sys/kernel/kptr_restrict'
   ```



- setting cpu freq
    ```
    sudo vim /etc/default/cpufrequtils

    ENABLE="true"
    GOVERNOR="powersave"
    MAX_SPEED=2.61GHz
    MIN_SPEED=2.60GHz
    ```
- service restart
    ```
    sudo service cpufrequtils restart
    ```
