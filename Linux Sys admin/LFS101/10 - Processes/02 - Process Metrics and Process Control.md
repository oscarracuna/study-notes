
# Load Averages
It's the average of the load number for a given period of time.
It takes into account processes that are:
- Actively running on a CPU.
- Considered runnable, but waiting on the run queue for a CPU to become available.
- Sleeping - waiting for some kind of resource (like I/O) to become available.

You can check the load average by running `w` `top` or `uptime`.
![[Pasted image 20260118165826.png]]

# Interpreting Load Averages
You see three numbers, let's use 0.45, 0.17 and 0.12 as examples on a single CPU system.

- 0.45: For the last minute the system has been 45% utilized on average.
- 0.17: For the last 5 minutes utilization has been 17%.
- 0.12: For the last 15 minutes utilization has been 12%.

If we have more than one CPU, we would divide the load average number by the number of CPUs. So if we had 4 CPUs, we can see a 1 min load average of up to 4.00.


# Background and Foreground Processes
Linux supports background and foreground job processing. A job is a command launched from a terminal window. Foreground jobs run directly form the shell, and when one foreground job is running, other jobs need to wait for shell access. 

You can send a job to run in the background, but it will execute at a lower at a lower priority, but you can do other things in the meantime.

You can use `CTRL+Z` to suspend a foreground job (send it to background) and `CTRL+C` to terminate it. You can also use `bg` to run a suspended process in the background or `fg` to run a background process in the foreground.

# Managing Jobs
The `jobs` utility displays all jobs running in the background.
`jobs -l` displays the PID as well.
The background jobs are connected to the terminal window, so if you log off, the jobs utility will not show the ones started from that window.
![[Pasted image 20260118171137.png]]

