FIFO UVM-Based Verification Environment
Project Overview
This repository contains a robust and reusable UVM-based verification environment for a Synchronous FIFO memory module. The environment is designed to verify the design using constrained random stimulus, functional coverage, and a scoreboarding mechanism to ensure 100% design correctness.

Architecture
The verification environment follows the standard UVM hierarchy:

Design Under Test (DUT): Synchronous FIFO memory.

UVM Testbench Components:

Sequencer: Manages data transaction flow.

Driver: Converts transactions into signal-level transitions on the interface.

Monitor: Samples interface signals and converts them back into transactions.

Agent: Encapsulates the Sequencer, Driver, and Monitor.

Scoreboard: Validates DUT output against a reference model.

Environment: Connects agents and scoreboards into a unified test system.

Key Features
Constrained Random Testing: Automated generation of scenarios including FIFO Full, Empty, and Wrap-around conditions.

Functional Coverage: Covergroups designed to track signal transitions and FIFO states.

SystemVerilog Assertions (SVA): Protocol checking for overflow, underflow, and reset behavior.

Parameterizable Design: Support for varying FIFO depths and data widths.

Repository Structure
rtl/: Contains the Verilog/SystemVerilog design source files.

tb/: Includes the UVM Environment, Agents, Sequences, and Test classes.

sim/: Contains simulation scripts and wave configurations.

top.sv: The top-level testbench module and virtual interface.

Tools and Prerequisites
Language: SystemVerilog, UVM 1.2

Simulators: Compatible with Siemens QuestaSim, Cadence Xcelium, or Synopsys VCS.

Methodology: Universal Verification Methodology (UVM).

Simulation Instructions
To execute the testbench in a command-line environment using a standard simulator:

Compile the files:
vlog -f files.f

Run the simulation:
vsim -c top_tb +UVM_TESTNAME=fifo_random_test -do "run -all; quit"

Verification Summary
Logic Verification: All read and write operations validated.

Flag Accuracy: Full, Empty, and Almost-Full flags verified under stress.

Corner Cases: Simultaneous read/write and overflow handled correctly.

Coverage: Achieved target functional and code coverage.
