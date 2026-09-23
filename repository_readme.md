# Empirical Profiling of Bubble Sort Variants (`py-spy`)

> **Course:** 02AML204 – Introduction to Artificial Intelligence  
> **Assignment:** SLE-2 Profiling Report (Empirical Performance Analysis)  
> **Author:** Mahamadsiddik M.Sharif Mulla 
> **Tool Used:** `py-spy` (Sampling Profiler for Python)

---

## 📌 Project Overview

This project presents an empirical performance analysis comparing two implementations of the **Bubble Sort** algorithm using sampling profiling with `py-spy`:

1. **Unoptimized Bubble Sort:** Standard quadratic $O(N^2)$ algorithm running all inner loop iterations regardless of array order.
2. **Optimized Bubble Sort (Early-Stop):** Employs a boolean `swapped` flag to detect sorted passes early, providing $O(N)$ best-case complexity.

The objective is to measure real execution performance, capture interactive flame graphs, and analyze why algorithmic optimizations yield specific speedups under pseudo-random workloads.

---

## 📁 Repository Structure

```text
.
├── sort.py                      # Main Python script containing both algorithm implementations & benchmark runner
├── profile_flamegraph.svg       # Generated py-spy flame graph visualization
├── SLE2_PRN_KetanGajananToraskar.docx # Formatted Word report submitted for SLE-2
└── README.md                    # Project documentation
```

---

## ⚙️ Requirements & Installation

- **Python:** 3.8+
- **Profiler:** `py-spy`

### Installing `py-spy`

```bash
pip install py-spy
```

*Note: On Windows, running `py-spy` requires Administrative privileges to sample process memory.*

---

## 🚀 How to Run the Benchmark & Profiler

### 1. Execute Benchmark Directly
To run the benchmarking script without active sampling:
```bash
python sort.py
```

### 2. Profile with `py-spy` in Git Bash (Windows)

1. Open **Git Bash** by right-clicking and selecting **Run as Administrator**.
2. Navigate to your project directory:
   ```bash
   cd /c/path/to/your/repository
   ```
3. Run `py-spy` to capture a sampling rate of 100 Hz and output a flame graph SVG:
   ```bash
   py-spy record -o profile_flamegraph.svg --rate 100 -- python sort.py
   ```
4. Open the resulting `profile_flamegraph.svg` file in any modern web browser (Chrome, Edge, Firefox) to explore function stack frames.

---

## 📊 Benchmark Results

- **Input Dataset:** $10 \times$ independent pseudo-random integer arrays (`random.randint(1, 100000)`)
- **Array Size ($N$):** 3,000 integers per run

| Metric | Unoptimized Bubble Sort | Optimized Bubble Sort (Early Stop) | Difference / Winner |
| :--- | :--- | :--- | :--- |
| **Total Execution Time (10 Runs)** | `4.18 seconds` | `3.93 seconds` | **Optimized (~6.0% faster)** |
| **Average Time per Run** | `0.418 seconds` | `0.393 seconds` | **Optimized** |
| **Total Comparisons** | $44,985,000$ | $\approx 44,985,000$ | Equivalent |
| **Best-Case Complexity** | $\mathcal{O}(N^2)$ | $\mathcal{O}(N)$ | **Optimized** |
| **Worst-Case Complexity** | $\mathcal{O}(N^2)$ | $\mathcal{O}(N^2)$ | Equivalent |

---

## 🧠 Performance Justification

1. **Why is the performance difference small (~6%)?**
   - On purely pseudo-random input arrays, numbers are out of order across almost all outer iterations.
   - The early termination condition (`if not swapped: break`) rarely fires because swaps occur during almost every pass.
   - As a result, both algorithms execute the full $\frac{N(N-1)}{2} = 4,498,500$ comparisons per array. The slight speed advantage ($\approx 0.25\text{s}$) is due to interpreter branch prediction and lower stack overhead.

2. **When does the Early-Stop optimization shine?**
   - On **sorted** or **nearly sorted** datasets, the early-stop mechanism drops execution complexity to $\mathcal{O}(N)$ after 1–2 passes, completing in milliseconds while the unoptimized version continues running for the full $O(N^2)$ duration.

---

## 🤖 AI Contribution Log

| Role | Contributor | Task / Output |
| :--- | :--- | :--- |
| **AI Assiastant** | Gemini / ChatGPT | Boilerplate Python benchmarking code, `py-spy` Git Bash command syntax, report structure formatting. |
| **Human Author** | Ketan G. Toraskar | Environment setup, running administrative terminal commands, data collection, empirical flame graph analysis. |

---

## 📄 License
This repository is created for academic coursework under **02AML204 - Introduction to Artificial Intelligence**.
