C++ CPU Scheduling Algorithm Simulator

This project is a C++ implementation of various CPU scheduling algorithms. It's designed to simulate how a set of processes would be handled by different schedulers, allowing for analysis and visualization of their performance based on a given input file.

Algorithms Implemented

This simulator includes the following scheduling algorithms:

1. First-Come, First-Serve (FCFS): A non-preemptive algorithm where processes are executed in the order they arrive.

2. Round Robin (RR): A preemptive algorithm where each process is given a fixed time slice (quantum). This implementation supports a variable quantum (e.g., 2-4 for a quantum of 4).

3. Shortest Process Next (SPN): A non-preemptive algorithm that selects the waiting process with the smallest execution (burst) time.

4. Shortest Remaining Time (SRT): The preemptive version of SPN. The scheduler switches to a new process if it has a shorter remaining time than the currently executing process.

5. Highest Response Ratio Next (HRRN): A non-preemptive algorithm that prioritizes processes based on their "response ratio" (waiting time + burst time) / burst time. This helps prevent the starvation of longer processes.

6. Feedback (FB-1): A preemptive, multi-level queue scheduler where all queues use a quantum of q=1. Processes move to lower-priority queues after their time slice expires.

7. Feedback (FB-2i): A feedback scheduler where the quantum doubles at each lower-priority level (i.e., q = 2^i for level i).

8. Aging: A preemptive, priority-based scheduler that prevents starvation by incrementally increasing the priority of processes that are waiting. The quantum q is a parameter (e.g., 8-1 for q=1).

🚀 Getting Started

Prerequisites

You will need a C++ compiler, such as g++ (part of the GCC) or clang.

Building

Clone the repository:

git clone [https://github.com/your-username/CPU-Scheduling-Algorithms.git](https://github.com/your-username/CPU-Scheduling-Algorithms.git)
cd CPU-Scheduling-Algorithms


Compile the project:
(Assuming your main file is main.cpp. Adjust as needed.)

g++ main.cpp -o scheduler -std=c++11


This will create an executable file named scheduler.

Usage

The simulator is run from the command line and reads its configuration from an input file. You can redirect a test file to the program's standard input.

./scheduler < path/to/input_file.txt


Example using a provided test case:

./scheduler < testcases/testcase_1.txt


📝 Input File Format

The simulator expects a very specific input file format to define the simulation parameters and process list.

Line 1: Output Mode

trace: Provides a step-by-step visualization of which process is running at each time instant.

stats: Provides a final summary table of performance metrics (e.g., turnaround time, waiting time) for each simulated algorithm.

Line 2: Algorithms to Run

A comma-separated list of algorithm codes (from the list above) to simulate.

For Round Robin (2) and Aging (8), specify the quantum with a dash:

Example: 1,2-4,3,8-1 would run FCFS, RR (quantum=4), SPN, and Aging (quantum=1).

Line 3: Last Simulation Instant

An integer specifying the time-unit to end the simulation (e.g., 100).

Line 4: Process Count

An integer specifying the total number of processes to follow.

Line 5...N: Process Descriptions

Each of the next N lines defines one process.

The format depends on the algorithms being run:

For Algorithms 1-7 (FCFS, RR, SPN, SRT, HRRN, FB):

ProcessName,ArrivalTime,ServiceTime


Example: P1,0,30

For Algorithm 8 (Aging):

ProcessName,ArrivalTime,Priority


Example: P1,0,5

Note: Processes are assumed to be pre-sorted by arrival time in the input file. If arrival times are equal, the process with the lower priority is assumed to arrive first.

Contributors

Mohd Kaif
