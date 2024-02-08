Incident Response Script

Objective

The script is designed to automate the investigation and isolation of a suspicious host identified by its IP address.

Skills Learned

-Python Programming: Enhanced skills in Python scripting, utilizing its syntax and libraries.
-Concurrent Execution: Learned concurrent programming techniques using ThreadPoolExecutor for parallel task execution.
-Network Investigation: Acquired basic network investigation skills through commands like ping and nslookup.
-Network Isolation: Explored network isolation methods, employing tools like iptables to restrict network access.
-Error Handling & Troubleshooting: Developed proficiency in error handling, timeout management, and debugging techniques.

Tools Used

-Python: The core programming language used for scripting and executing the logic of the script.
-Subprocess Module: A built-in Python module used to spawn new processes, connect to their input/output/error pipes, and obtain their return codes.
-concurrent.futures.ThreadPoolExecutor: A part of the concurrent.futures module used for managing a pool of threads to execute tasks concurrently.
-ping Command: A network utility tool used to test the reachability of a host on an Internet Protocol (IP) network.
-nslookup Command: A network administration command-line tool used for querying the Domain Name System (DNS) to obtain domain name or IP address mapping.
-iptables Command: A user-space utility program used to configure network packet filtering rules in the Linux kernel's netfilter frameworkdrag & drop screenshots here or use imgur  and reference them using imgsrc

Steps

1.  ![PIR pic#1](https://github.com/CyberneticJosh96/Incident-Response-Script/assets/146404458/4873caac-f25f-4fe4-b59f-fd971d2989fb)

1A. The script employs essential Python modules for system interaction. subprocess manages process execution, os provides OS-related functionality, time introduces delays for     simulation, and ThreadPoolExecutor from concurrent.futures enables parallel execution of investigation and isolation tasks.

2.   ![pir pic#2](https://github.com/CyberneticJosh96/Incident-Response-Script/assets/146404458/1084db38-d706-4c1c-8c71-20ec8f190d9a)

2A. This function is responsible for executing a given command and capturing its output.
Command Execution: subprocess.run is used to execute the specified command. The shell=True parameter allows the use of shell syntax, and capture_output=True captures the command's output.
Return Format: The function returns a formatted string containing both the executed command and its output.

3.  ![pir pic #3](https://github.com/CyberneticJosh96/Incident-Response-Script/assets/146404458/d6b59231-2b65-4033-a8ed-a7eb15479095)

3A. This function orchestrates the investigation of a host by executing a list of investigation commands.
Investigation Commands: A list of investigation commands is defined. In this example, it includes commands like ping and nslookup.
Parallel Execution: ThreadPoolExecutor is utilized to execute the investigation commands in parallel, leveraging the investigate_command function.
Result Handling: The results are printed or logged.

4. ![PIR pic #5](https://github.com/CyberneticJosh96/Incident-Response-Script/assets/146404458/167b8ac6-08f9-45c2-b92a-66ceae261b15)

4A. Initialization: Assigns the IP address of the suspicious host.
Incident Detection: Prints a message signaling the detection.
Investigation: Invokes investigate_host to scrutinize the host concurrently. Simulated Delay: Introduces a 5-second delay for investigation simulation.
Isolation: Invokes isolate_host for host isolation if needed.
Completion Message: Prints a message signifying the conclusion of the incident response.
