# PGC Lab — KLE Technological University

### Parallel and GPU Computing Laboratory Index

This repository serves as the master directory and navigation index for all laboratory experiments and course projects completed in the **Parallel and GPU Computing (PGC) Laboratory** course at **KLE Technological University**.

Each experiment and project is maintained as an independent, fully self-contained repository with its own dedicated source code, build scripts, benchmarks, profiler traces, and verified execution screenshots.

---

## Laboratory Experiments

| Exp No. | Experiment Title | Description | Repository Link |
|:---:|:---|:---|:---:|
| **Exp 1** | **Parallel Matrix Multiplication Across Computing Paradigms** | Comparative performance evaluation of dense matrix multiplication ($4000 \times 4000$) across single-threaded Sequential CPU, OpenMP multi-threaded shared memory, Open MPI distributed cluster (4 nodes), and NVIDIA CUDA massively parallel SIMT architectures. | [Parallel-Matrix-Multiplication](https://github.com/Arihant-57/Parallel-Matrix-Multiplication) |
| **Exp 2** | **Multithreaded Programming Using Pthreads and OpenMP** | Investigation of core concurrency concepts: thread lifecycle management, work chunking, race hazards, mutex locking (`pthread_mutex_t`), OpenMP work-sharing directives, critical sections, barrier synchronization, and speedup/efficiency scaling up to 16 threads. | [Multithreaded-Pthreads-OpenMP](https://github.com/Arihant-57/Multithreaded-Pthreads-OpenMP) |
| **Exp 3** | **Synchronization Mechanisms in Parallel Programs** | Evaluation of shared-memory synchronization: data race conditions, OpenMP critical sections (`#pragma omp critical`), hardware-supported atomic updates (`#pragma omp atomic`), OpenMP locks (`omp_lock_t`), barrier synchronization, and POSIX semaphores, benchmarked across 1–8 threads for 10M increments. | [PGC-L3-Synchronization-Mechanisms](https://github.com/Arihant-57/PGC-L3-Synchronization-Mechanisms) |
| **Exp 4** | **Snooping Cache Coherence Protocols and NUMA Memory Performance** | Evaluation of multi-core memory architectures: snooping cache coherence simulation (`MSI`, `MESI`, `MOESI`), 64-byte cache-line false sharing analysis (`adjacent` vs `padded` memory layouts), and NUMA memory access policy benchmark using `numactl`. | [PGC-L4-Cache-Coherence-NUMA](https://github.com/Arihant-57/PGC-L4-Cache-Coherence-NUMA) |
| **Exp 5** | **Neural Network Forward-Pass Layers in CUDA** | Implementation and numerical verification of dense feed-forward neural network layers ($X \times W_1 + b_1 \to \text{ReLU} \to Z_1 \times W_2 + b_2 \to \text{Sigmoid}$) using custom CUDA C++ kernels with CPU reference ground-truth validation and execution timing. | [PGC-L5-NeuralNetwork-CUDA](https://github.com/Arihant-57/PGC-L5-NeuralNetwork-CUDA) |
| **Exp 6** | **Memory Optimization in CUDA** | Optimization of GPU memory access patterns: comparing uncoalesced global memory access against shared-memory tiled matrix transpose with $+1$ column padding (`tile[32][33]`) to eliminate bank conflicts (achieving 2.49x speedup), along with naive matrix multiplication profiling. | [PGC-L6-CUDA-Memory-Optimization](https://github.com/Arihant-57/PGC-L6-CUDA-Memory-Optimization) |
| **Exp 7** | **Profiling and GPU Utilization Analysis** | End-to-end performance profiling of a multi-batch deep learning workload using PyTorch Profiler and Chrome trace analysis. Eliminates PCIe/SM idle bubbles and achieves 43.10 ms of copy-compute overlap and 95.16% GPU utilization via pinned host memory, dual CUDA streams, and asynchronous double buffering. | [PGC-L7-GPU-Profiling-Utilization](https://github.com/Arihant-57/PGC-L7-GPU-Profiling-Utilization) |

---

## PGC Course Projects and Evaluation Themes

Specialized course evaluation projects and thematic laboratory implementations:

| Project / Theme | Project Title | Description | Repository Link |
|:---|:---|:---|:---:|
| **Course Mini-Project (Topic 10)** | **CPU vs. GPU Data Processing Performance Analysis** | Evaluation of large-scale element-wise vector operations across Sequential CPU, OpenMP multi-threading (16 threads), and NVIDIA CUDA GPU across 10M, 50M, and 100M data points, analyzing hardware scaling boundaries and memory-bandwidth saturation. | [CPU-VS-GPU-Data-Processing](https://github.com/Arihant-57/CPU-VS-GPU-Data-Processing) |
| **CUDA Evaluation Project (Theme 10)** | **Numerically Stable Softmax and Kernel Fusion in CUDA** | High-performance implementation of Transformer Softmax layer. Compares a 3-kernel baseline against a single fused kernel with dynamic on-chip shared-memory caching and tree reductions, preventing FP32 overflow/underflow and cutting DRAM traffic by 50%. | [cuda-softmax-kernel-fusion](https://github.com/Arihant-57/cuda-softmax-kernel-fusion) |

---

## Primary Hardware and Software Specifications

The practical experiments and benchmarks across these repositories were executed and verified on the following hardware setup:

- **GPU**: NVIDIA GeForce RTX 3050 6GB Laptop GPU (Ampere architecture, Compute Capability 8.6, 2048 CUDA Cores)
- **CPU**: Intel Core i7-13650HX (14 cores, 20 threads) / Multi-Core Workstation
- **Operating Systems**: Microsoft Windows 11 64-bit / Ubuntu Linux (WSL2 / Dedicated)
- **Toolchains & Compilers**: NVIDIA CUDA Toolkit (`nvcc`), Microsoft Visual Studio C++ (`cl`), GNU Compiler Collection (`gcc` / `g++`)
- **Libraries & APIs**: OpenMP, Open MPI, POSIX Threads (Pthreads), PyTorch (`torch.profiler`), NVIDIA SMI
