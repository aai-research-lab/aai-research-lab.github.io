---
layout: post
title: AAI Research Lab acquires the first GPU-capable HPC cluster at CSUDH
date: 2025-01-31 00:00:00-0800
inline: false
related_posts: false
---

AAI Research Lab has acquired and installed the first High-Performance Computing cluster with GPU capabilities at California State University, Dominguez Hills.

This machine enables computational research and skill development at a scale not previously possible for students at CSUDH — molecular dynamics, protein design, and machine learning workloads that would otherwise have to be sent off campus.

---

### The system

A PSSC Labs PowerWulf ZXR1 cluster, comprising a head node and a GPU compute node:

|             |                                                                                                             |
| ----------- | ----------------------------------------------------------------------------------------------------------- |
| **CPU**     | 96 AMD EPYC cores (192 threads) — 32 cores at 3.0 GHz on the head node, 64 cores at 2.6 GHz on the GPU node |
| **GPU**     | 2 × NVIDIA L40S, 48 GB GDDR6 each — 96 GB of GPU memory and 36,352 CUDA cores                               |
| **Memory**  | 384 GB DDR4 ECC — 128 GB on the head node, 256 GB on the GPU node                                           |
| **Storage** | ~5.76 TB raw enterprise flash, hardware RAID                                                                |
| **Network** | 10 Gbps backplane, with a separate management network and IPMI on every node                                |

The software stack runs on Linux with the SLURM scheduler, an Open OnDemand portal for browser-based access, Apptainer for portable containers, OpenMPI with GNU, Intel and AMD compilers, and Prometheus and Grafana for monitoring. The cluster is designed to be extended — processors, memory, storage and additional GPUs can all be added as our computing needs grow.

### Thanks

We are grateful to the leadership of the College of Natural and Behavioral Sciences and California State University, Dominguez Hills for this investment, and to CSUDH Information Technology for their technical support over the three months leading up to installation.

[Join us](/join/).
