# LUT_Optimization
Look-Up Table (LUT) Optimization for Memory-Based Computation using Vitis HLS
# LUT Optimization for Memory-Based Computation

This project explores the use of Look-Up Tables (LUTs) to accelerate arithmetic computations (like squaring a number) using Vitis HLS, with hardware optimization directives to reduce latency and resource usage.

---

## Objective

- Replace arithmetic operations with LUT-based memory access.
- Optimize the design using Vitis HLS directives (e.g., pipelining).
- Evaluate the performance benefits in terms of latency, initiation interval, and hardware resources.

---

## Background

Look-Up Tables (LUTs) are commonly used in digital hardware design to store precomputed results of functions, thus avoiding real-time computation. This approach is particularly effective for:

- Power-efficient design
- Reduced latency in computation
- Constant-time operation irrespective of function complexity

---

## Implementation

### ➤ Functionality:
The system computes the square of numbers using a precomputed LUT stored in BRAM.

### ➤ Development Environment:
- **Tool:** Vitis HLS 2022.2
- **Language:** C++
- **Target:** FPGA hardware acceleration

---

## Project Structure
LUT_Optimization/
├── src/                   # Source code for LUT-based computation
│   └── lut_square.cpp     # C++ implementation for LUT-based squaring using Vitis HLS
│
├── results/               # Output reports and screenshots
│   └── results.png        # Screenshot of optimization report 
│
├── README.md              # Project overview and instructions

---

## Optimization

### Directives Applied:
- `#pragma HLS PIPELINE`: Reduces initiation interval to 1
- `#pragma HLS RESOURCE variable=lut core=ROM_1P_BRAM`: Forces BRAM implementation
- `#pragma HLS ARRAY_PARTITION` (if needed): Improves parallel access

### Optimization Results (from `results.png`):
- **Initiation Interval (II):** 1
- **Latency:** 2 cycles
- **Throughput:** 1 result per cycle
- **BRAM usage:** Efficient due to LUT usage

## Results
Added and named as results.png
