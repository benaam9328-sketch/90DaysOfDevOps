---------Day2 Notes--------------

Topic 1- The core components of Linux (kernel, user space, init/systemd)
         Linux is an Operating System created by linus torvalds in 1991 and inspired from UNIX.Linux is Open source and secure used in 90% of productions servers.
         Linux has 3 core components that is -
         Application <---->Shell <------> Kernel
         1) Application - The apps and programs that you run.
         2) Shell- Interface between Kernel and application, helps application to interact with kernel.
         3) Kernel- heart of the OS, here the actual code lies and kernel interacts with hardware to get the work done.
         Shell----sends message in binary--->Kernel

         User Space- The space where the application runs, its not a phsical space its a logical space defined for apps and programs.
         
         init/systemd-This is the first command loaded by bootloader , it has pid 1 .systemd process starts all the other services after boot or in case of service failure.
                       if we dont have systemd then we have to manually start each process.

  Topic 2- How processes are created and managed
          process is a running program, its created when we start any application or program.its managed by linux as follows-
          App start---process created--->Cpu scheduling(allocates Cpu time to the process how long it will have CPU)--->Context Swutching(switches cpu between processes; store mem stat etc)
          --->Process management(manages process state Zombie, Running,terminated, sleep)--->Memory allocation(memory is allocated individually to the process; if one crashes other is running)
          ---->priority management(process given resources based on priority ; Video call> Bg update)-->process kill--->process termination(all resources get free).
          running- when process is active and currently running
          sleep- process is in idle statewaiting for some resources or input.
          zombie- the process is not using any resource (just a little memory) but pid not freed its still there .no issue unless too many zombie process is there.
          stop- when process is in stopped state/paused temporarily.


  Topic 3-What systemd does and why it matters
          Systemd is a system deamon , its a process which has pid 1 which is started by the bootloader its work is to start other processes.
          it matters a lot if its not there we have to manually start each and every process.
