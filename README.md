# CPU Scheduling Algorithms Simulator (C++)

This project is a **C++ implementation** of various **CPU scheduling algorithms**.  
It simulates how processes are handled by different schedulers and provides **trace** and **statistical outputs** for performance analysis.

---

## 🚀 Features

✅ Simulates multiple classical CPU Scheduling Algorithms  
✅ Supports **trace** (timeline visualization) and **stats** (performance summary) modes  
✅ Configurable quantum for RR and Aging algorithms  
✅ Reads processes from a formatted input file  
✅ Modular, extendable, and easy to visualize scheduling behavior  

---

## 🧩 Algorithms Implemented

| ID | Algorithm | Type | Description |
|----|------------|------|-------------|
| **1** | **FCFS (First Come First Serve)** | Non-preemptive | Processes are executed in the order they arrive. |
| **2** | **Round Robin (RR)** | Preemptive | Each process gets a fixed time slice (quantum). |
| **3** | **SPN (Shortest Process Next)** | Non-preemptive | Executes the process with the smallest burst time. |
| **4** | **SRT (Shortest Remaining Time)** | Preemptive | Chooses process with the least remaining burst time. |
| **5** | **HRRN (Highest Response Ratio Next)** | Non-preemptive | Selects process with highest response ratio. |
| **6** | **FB-1 (Feedback)** | Preemptive | Multi-level queue with equal quantum = 1. |
| **7** | **FB-2i (Feedback Variable)** | Preemptive | Feedback scheduler with doubling quantum at each level. |
| **8** | **Aging** | Preemptive | Priority-based; waiting processes gradually increase in priority to prevent starvation. |

---

## 🛠️ Prerequisites

- **C++ compiler** such as `g++` (from GCC) or `clang`.
- A terminal or IDE supporting C++ (e.g., VS Code, Code::Blocks).

---

## ⚙️ Installation & Build

```bash
# Clone the repository
git clone https://github.com/kaifcode2003/CPU-Scheduling-Algorithms.git
cd CPU-Scheduling-Algorithms

# Compile the simulator
g++ main.cpp -o scheduler -std=c++11

▶️ Usage

Run the simulator from the command line, redirecting an input file:
./scheduler < path/to/input_file.txt
Example:
./scheduler < testcases/testcase_1.txt
