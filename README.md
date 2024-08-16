# CPU Scheduling Algorithms Simulator

This project simulates various CPU scheduling algorithms, including FCFS, Round Robin, SPN, SRT, HRRN, Feedback Queues, and Aging. The simulator can display a trace of process executions or provide detailed statistics of the execution.

## Table of Contents
- [Features](#features)
- [Usage](#usage)
- [Code Structure](#code-structure)
- [Supported Algorithms](#supported-algorithms)
- [Sample Input/Output](#sample-inputoutput)
- [License](#license)

## Features
- **Multiple Scheduling Algorithms**: Supports a variety of CPU scheduling algorithms.
- **Operation Modes**: Can run in trace mode to visualize process execution or statistics mode for performance metrics.
- **Modular Design**: The code is designed for easy expansion and modification.
- **Automatic Parsing**: Input data is parsed automatically, simplifying user interaction.

## Usage

1. **Compile the Code**:
    ```bash
    g++ -o scheduler main.cpp
    ```

2. **Run the Code**:
    ```bash
    ./scheduler
    ```

3. **Input Format**:
   - The program expects input in the following format:
     ```
     <operation> <algorithms> <last_instant> <process_count>
     <process_1>
     <process_2>
     ...
     ```
   - Example:
     ```
     trace FCFS,RR-4,SPN 20 3
     P1,0,5
     P2,2,3
     P3,4,1
     ```

## Code Structure

- **parser.h**: Handles the parsing of input data and initialization of global variables.
- **main.cpp**: Contains the implementation of different scheduling algorithms and the main execution logic.
- **Global Constants**:
  - `TRACE`: Mode to visualize the timeline of process execution.
  - `SHOW_STATISTICS`: Mode to display execution statistics.

## Supported Algorithms
The following scheduling algorithms are implemented:

1. **FCFS**: First Come First Serve.
2. **RR**: Round Robin (requires a time quantum).
3. **SPN**: Shortest Process Next.
4. **SRT**: Shortest Remaining Time.
5. **HRRN**: Highest Response Ratio Next.
6. **FB-1**: Feedback Queue with a single-level feedback.
7. **FB-2i**: Feedback Queue with increasing quantum by powers of 2.
8. **Aging**: Priority aging algorithm.

## Sample Input/Output

- **Sample Input**:

stats FCFS,RR-4,SPN 20 3
P1,0,5
P2,2,3
P3,4,1

- **Sample Output**:
FCFS
Process | P1 | P2 | P3 |
Arrival | 0 | 2 | 4 |
Service | 5 | 3 | 1 | Mean|
Finish | 5 | 8 | 9 |-----|
Turnaround | 5 | 6 | 5 | 5.33|
NormTurn | 1.00 | 2.00 | 5.00 | 2.67|
