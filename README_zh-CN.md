# ClawOS
专为 **OpenClaw** 设计的**只读不可变、强隔离、原生 AI 加速操作系统**。

[![License](https://img.shields.io/badge/License-Apache2.0-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-x86_64%20%7C%20arm64-brightgreen)](/)
[![GPU](https://img.shields.io/badge/GPU-NVIDIA%20%7C%20AMD-orange)](/)

[[简体中文](README_zh-CN.md)] [[English](README.md)]

---

## 🔥 核心理念
OpenClaw 功能强大但风险极高，容易误删系统、破坏文件、权限越界。
**ClawOS 从底层设计：让 OpenClaw 绝对安全，同时自带完整本地大模型能力。**

- 系统只读，不可破坏
- 内核级 UID/GID 工作区隔离
- 内置统一 AI 网关
- 双架构 + 双显卡全加速
- A/B 分区安全 OTA

---

## ✨ 特性

### 🔒 安全与隔离
- **只读 SquashFS 根文件系统**
  系统、驱动、OpenClaw、AI 引擎全部固化，无法被篡改或删除。
- **UID/GID 权限隔离**
  每个工作区独立用户/组，仅能访问自身挂载目录，内核级权限锁死。
- **独立工作区挂载**
  多任务数据完全隔离，互不污染，不越权。
- **OpenClaw 非 root 运行**
  最小权限 + seccomp 限制，禁止提权、禁止挂载、禁止跨目录访问。

### 🤖 原生本地 AI
- **内置统一大模型网关**
  一套接口兼容：
  - Ollama
  - llama.cpp
  - SGLang
  - vLLM
- **开箱即用模型**
  - Qwen 3.5
  - Gemma 4
- **OpenAI 兼容 API**
  `/v1/chat/completions` 直接对接现有应用。

### 🧩 跨平台硬件加速
- **架构支持**
  - x86_64 (Intel / AMD)
  - arm64 (Apple / 服务器 / 嵌入式)
- **显卡加速**
  - NVIDIA：CUDA / TensorRT
  - AMD：ROCm / OpenCL
- 全引擎、全模型自动硬件加速

### 🚀 安全 OTA 更新
- **A/B 双分区架构**
- 系统 / AI 引擎 / 模型 / 驱动 全支持 OTA
- 更新失败自动回滚，**永不变砖**
- 新模型、新版本、驱动优化，后台静默推送
