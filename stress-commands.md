Here are some basic stress commands you can use:

1. **CPU Stress**: 
   ```
   stress --cpu 1
   ```
   This command stresses the CPU by spinning a specified number of worker threads.

2. **Memory Stress**:
   ```
   stress --vm 1 --vm-bytes 256M
   ```
   This command stresses the memory by allocating and using a specified amount of memory.

3. **I/O Stress**:
   ```
   stress --io 1
   ```
   This command stresses the I/O subsystem by performing random I/O operations.

4. **Disk Stress**:
   ```
   stress --hdd 1
   ```
   This command stresses the disk by performing read/write operations on the disk.

5. **Network Stress**:
   ```
   stress --net 1
   ```
   This command stresses the network by generating network traffic.

These commands can be combined with options like `--timeout` to specify the duration of the stress test and `--verbose` to get more detailed output.
Adjust the parameters as needed based on your requirements and the resources available on your system.
