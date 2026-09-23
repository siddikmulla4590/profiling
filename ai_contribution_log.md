# AI & Human Contribution Log (SLE-2)

> **Course:** 02AML204 – Introduction to Artificial Intelligence  
> **Assignment:** SLE-2 Profiling Report (Empirical Performance Analysis)  
> **Student Name:** Mahamadsiddik Mahamadsharif Mulla
> **PRN:** 25UAM054
> **Date:** September 22, 2026  

---

## 📌 Executive Summary

This log documents the breakdown of work between the **Student (Human Author)** and **AI Assistants (Gemini / ChatGPT)** during the execution of SLE-2. The primary objective was to measure, profile, and justify the performance differences between **Unoptimized Bubble Sort** and **Optimized Bubble Sort (Early Stop)** using `py-spy`.

---

## 🛠️ Detailed Task Breakdown

| Task / Phase | Student Contribution (Siddik) | AI Contribution (Gemini / ChatGPT) | Ownership & Validation |
| :--- | :--- | :--- | :--- |
| **1. Code Development** | Specified requirements (3,000 array size, 10 benchmark runs, sorting logic). Tested script execution locally. | Wrote initial Python implementation for unoptimized and optimized Bubble Sort algorithms (`sort.py`). | **Student Verified:** Confirmed array logic and dataset generation worked without errors. |
| **2. Profiling Setup & CLI Commands** | Configured Git Bash on Windows, ran terminal as Administrator, and executed profiling commands. | Provided exact CLI commands (`py-spy record -o profile_flamegraph.svg ...`) and Git Bash execution tips. | **Student Executed:** Manually ran the profiler and generated the SVG flame graph. |
| **3. Data Collection** | Extracted exact timing metrics from terminal execution (3.93s vs 4.18s). | Interpreted the numbers and mathematically analyzed the total comparison count ($44,985,000$). | **Student Verified:** Measured real execution times on local system hardware. |
| **4. Analysis & Justification** | Validated that random input data causes minimal variance between algorithms. | Provided theoretical justification for $O(N^2)$ behavior on pseudo-random vs pre-sorted data. | **Student Owned:** Ensured justifications strictly aligned with measured empirical data. |
| **5. Documentation & Reporting** | Provided personal details, PRN, and verified submission guidelines. | Formatted content into official `.docx` report, `README.md`, and PDF formats. | **Student Finalized:** Reviewed final output before submission to Moodle. |

---

## 📊 Summary of Effort Allocation

```
Human Effort (Student)  : [██████████░░░░░░░░░░] 50%  (Execution, Environment Setup, Measurement, Verification)
AI Assistance           : [██████████░░░░░░░░░░] 50%  (Code Generation, Command Syntax, Report Formatting)
```

---

## 📜 Academic Honesty Statement

I confirm that all profiling experiments were executed locally on my machine using actual code. The numbers presented in the report reflect genuine execution data gathered via `py-spy`. AI tools were utilized solely as an educational assistant for code generation, syntax guidance, and document formatting.

**Student Signature:** Mahamadsiddik Mahamadsharif Mulla 
**Date:** September 22, 2026
