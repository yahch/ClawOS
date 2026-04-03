# ClawOS

An **immutable, read-only, strongly isolated, native AI-accelerated OS** built exclusively for **OpenClaw**.

[![License](https://img.shields.io/badge/License-Apache2.0-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-x86_64%20%7C%20arm64-brightgreen)](/)
[![GPU](https://img.shields.io/badge/GPU-NVIDIA%20%7C%20AMD-orange)](/)

---

## 🔥 Core Concept
OpenClaw is powerful but high-risk: it can accidentally delete system files, corrupt data, or escape containment.

**ClawOS is designed from the ground up to run OpenClaw safely, while including a full local AI stack out of the box.**

- Immutable, read-only system
- Kernel-level UID/GID workspace isolation
- Built-in unified AI gateway
- Cross-architecture & dual-GPU acceleration
- A/B partition safe OTA updates

---

## ✨ Features

### 🔒 Security & Isolation
- **Read-only SquashFS root**
  System, drivers, OpenClaw, and AI engines are all immutable — cannot be modified or deleted.
- **UID/GID permission isolation**
  Each workspace uses a dedicated user/group, with access limited to its own mount.
- **Per-workspace mount isolation**
  No cross-contamination between tasks or users.
- **OpenClaw runs as non-root**
  Minimal capabilities + seccomp restrictions; no privilege escalation, no cross-directory access.

### 🤖 Native Local AI
- **Unified AI Gateway**
  Single API compatible with:
  - Ollama
  - llama.cpp
  - SGLang
  - vLLM
- **Pre-built models included**
  - Qwen 3.5
  - Gemma 4
- **OpenAI-compatible API**
  `/v1/chat/completions` works with all standard clients.

### 🧩 Cross-Platform Hardware Acceleration
- **Architectures**
  - x86_64 (Intel / AMD)
  - arm64 (Apple / servers / embedded)
- **GPU Acceleration**
  - NVIDIA: CUDA / TensorRT
  - AMD: ROCm / OpenCL
- Automatic detection and acceleration for all engines & models

### 🚀 Safe OTA Updates
- **A/B dual-partition architecture**
- Full OTA for system, AI engines, models, and GPU drivers
- Automatic rollback on failure — **no bricking**
- Silent background updates for new models, versions, and optimizations
