# 🚀 OpenOCR-Engine

> Engineering Deployment Adapter for DeepSeek-OCR-2
> Run CUDA-Oriented Research Models on CPU / MPS / GPU — Safely & Reproducibly

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-2.x-orange)
![Transformers](https://img.shields.io/badge/Transformers-4.46.3-green)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## 📖 Overview

**OpenOCR-Engine** is an engineering-grade deployment adapter built around the DeepSeek-OCR-2 research model.

This project does NOT modify the original model architecture or training logic.
Instead, it provides a runtime compatibility and deployment layer that enables stable cross-device execution and production-style integration.

Many research models are:

* CUDA-dependent
* Version-fragile
* Research-environment oriented
* Not production-hardened

OpenOCR-Engine demonstrates how to productionize such models responsibly and non-invasively.

---

## 🔗 Upstream Attribution

This project is built as an engineering deployment adapter for:

DeepSeek-OCR-2 (original research model)

We do NOT claim authorship of:

* The model architecture
* Training methodology
* Pretrained weights
* Research contributions

All intellectual property related to the DeepSeek-OCR-2 model belongs to the original DeepSeek team.

This repository provides:

* Engineering adaptation layer
* Runtime compatibility patches
* Deployment infrastructure
* API & Web interface
* Cross-device execution support

For the original implementation, please refer to the official DeepSeek repository.

---

## 🎯 Why This Project Matters

Research Models ≠ Production Systems

Most open-source AI models:

* Assume CUDA availability
* Hard-code device calls
* Lack reproducible environments
* Provide unstable inference interfaces

OpenOCR-Engine demonstrates:

* Non-invasive engineering adaptation
* Runtime compatibility techniques
* Device abstraction design
* AI deployment architecture patterns

---

## 🧠 Core Engineering Concepts Demonstrated

### 1️⃣ Runtime Compatibility Layer

Implements safe runtime adaptation techniques such as:

* Intercepting `.cuda()` calls
* Adapting `torch.autocast` usage
* Enabling controlled CPU/MPS fallback

This avoids modifying upstream model source files.

---

### 2️⃣ Device Abstraction Strategy

Automatic hardware detection:

* CUDA (NVIDIA GPU)
* MPS (Apple Silicon)
* CPU fallback

Ensures consistent behavior across heterogeneous environments.

---

### 3️⃣ Dependency Stabilization

* Locked compatible transformer versions
* Reproducible environment setup
* Cache isolation strategy

Improves long-term maintainability.

---

### 4️⃣ Stable Inference Interface

Standardizes inference return structure for predictable downstream usage.

---

### 5️⃣ Deployment Enhancements

* Flask-based Web UI
* RESTful API interface
* Modular project structure
* Image preprocessing pipeline
* Prompt-layer abstraction
* History logging support

---

## 🏗 Architecture

```
User Interface
      ↓
Flask Server
      ↓
Model Adapter Layer
      ↓
DeepSeek-OCR-2
      ↓
Hardware (CUDA / MPS / CPU)
```

---

## 📊 Original vs Engineered Deployment Layer

| Feature             | Research Version | OpenOCR-Engine        |
| ------------------- | ---------------- | --------------------- |
| Device Support      | CUDA-oriented    | CUDA / MPS / CPU      |
| Inference Interface | Research-style   | Standardized          |
| Web Interface       | ❌                | ✅                     |
| REST API            | ❌                | ✅                     |
| Deployment Ready    | ❌                | ✅                     |
| Version Stability   | Fragile          | Locked & Reproducible |

---

## ⚡ Performance Reference

| Device   | Speed   | Memory Usage       |
| -------- | ------- | ------------------ |
| CUDA GPU | ~30 sec | ~6GB               |
| CPU      | 2–5 min | ~8–10GB            |
| MPS      | Partial | Hardware dependent |

*Performance varies depending on hardware configuration.*

---

## 📂 Project Structure

```
openocr-engine/
├── app_simple.py
├── model_adapter.py
├── config.py
├── hybrid_ocr_engine.py
├── app_api.py
├── templates/
├── uploads/
└── outputs/
```

---

## 🔧 Installation

```bash
pip install transformers==4.46.3 tokenizers==0.20.3
pip install torch torchvision
pip install flask pillow einops addict matplotlib
```

---

## ▶ Run

```bash
python app_simple.py
```

Access:

```
http://localhost:5003
```

---

## 🧪 Example Use Cases

Convert:

* Contracts
* Bidding documents
* Scanned PDFs
* Business paperwork

Into structured Markdown output.

---

## ⚖ Important Legal Notice

OpenOCR-Engine is an independent engineering project.

This repository does NOT:

* Redistribute DeepSeek pretrained weights
* Republish original DeepSeek source files
* Modify original DeepSeek model architecture
* Claim ownership of the DeepSeek-OCR-2 model

Users must:

* Obtain the original model from official sources
* Comply with the original DeepSeek license
* Respect upstream intellectual property

This repository provides a runtime engineering wrapper and deployment framework only.

---

## 📜 License

This repository (OpenOCR-Engine) is released under the MIT License.

However:

DeepSeek-OCR-2 model code and weights are subject to their original license.

This project does not override or replace upstream license terms.

Users must comply with:

* The MIT License of this repository
* The original DeepSeek license for model usage

---

## 🤝 Contributing

Pull requests are welcome.

If you find this project useful, consider starring ⭐ the repository.

---

你说得对 👍
上面中文版确实是“精简版”，不是完整对照翻译。

下面给你一份 **完整中文对照版（逐段完整翻译）**，结构和英文完全一致，你可以直接放在 README 末尾作为“完整中文版”。

---

# 🇨🇳 中文完整版

---

# 🚀 OpenOCR-Engine

> 面向 DeepSeek-OCR-2 的工程级部署适配层
> 让 CUDA 导向的研究模型安全、稳定地运行在 CPU / MPS / GPU 上

---

## 📖 项目概述

**OpenOCR-Engine** 是一个围绕 DeepSeek-OCR-2 构建的工程级部署适配层。

本项目**不会修改原始模型结构或训练逻辑**。
它通过构建运行时兼容层与部署适配层，实现跨设备稳定运行与生产级系统集成。

大多数研究型模型通常具有以下特点：

* 强依赖 CUDA
* 对依赖版本敏感
* 面向实验环境设计
* 不具备生产级稳定性

OpenOCR-Engine 展示了如何在**不侵入原始源码的前提下**，对研究模型进行工程化部署。

---

## 🔗 上游项目说明

本项目基于以下研究模型构建工程部署适配层：

DeepSeek-OCR-2（原始研究模型）

我们不声明以下内容的所有权：

* 模型架构设计
* 训练方法
* 预训练权重
* 研究成果

DeepSeek-OCR-2 的全部知识产权归原 DeepSeek 团队所有。

本仓库仅提供：

* 工程适配层
* 运行时兼容补丁
* 部署架构
* API 与 Web 接口
* 跨设备执行支持

如需查看原始模型实现，请访问官方 DeepSeek 仓库。

---

## 🎯 为什么这个项目有价值

研究模型 ≠ 生产系统

大多数开源 AI 模型：

* 默认依赖 CUDA
* 存在硬编码设备调用
* 缺乏可复现环境
* 推理接口不稳定

OpenOCR-Engine 展示了：

* 非侵入式工程改造方法
* 运行时兼容技术
* 设备抽象设计模式
* AI 部署架构思路

---

## 🧠 核心工程思想展示

### 1️⃣ 运行时兼容层

通过安全的运行时适配技术实现：

* 拦截 `.cuda()` 调用
* 适配 `torch.autocast`
* 支持 CPU / MPS 自动回退

在不修改上游源码的情况下实现跨设备运行。

---

### 2️⃣ 设备抽象策略

自动检测并适配硬件环境：

* CUDA（NVIDIA GPU）
* MPS（Apple Silicon）
* CPU 备用执行

确保在不同硬件环境中行为一致。

---

### 3️⃣ 依赖稳定策略

* 锁定兼容的 transformers 版本
* 构建可复现环境
* 进行模块缓存隔离

提升长期可维护性。

---

### 4️⃣ 稳定推理接口

统一推理返回结构，确保下游系统可以稳定调用。

研究代码常常返回结构不统一，而生产系统必须拥有明确接口契约。

---

### 5️⃣ 部署增强能力

* 基于 Flask 的 Web 界面
* RESTful API 接口
* 模块化项目结构
* 图像预处理管线
* Prompt 抽象层设计
* 历史记录管理

将研究脚本转化为服务型系统架构。

---

## 🏗 系统架构

```
用户界面
      ↓
Flask 服务层
      ↓
模型适配层
      ↓
DeepSeek-OCR-2
      ↓
硬件执行层（CUDA / MPS / CPU）
```

---

## 📊 原始版本 vs 工程部署层

| 功能项      | 研究版本   | OpenOCR-Engine   |
| -------- | ------ | ---------------- |
| 设备支持     | CUDA导向 | CUDA / MPS / CPU |
| 推理接口     | 研究风格   | 标准化接口            |
| Web界面    | ❌      | ✅                |
| REST API | ❌      | ✅                |
| 部署可用性    | ❌      | ✅                |
| 版本稳定性    | 易碎     | 锁定 & 可复现         |

---

## ⚡ 性能参考

| 设备       | 推理速度  | 内存占用    |
| -------- | ----- | ------- |
| CUDA GPU | ~30秒  | ~6GB    |
| CPU      | 2–5分钟 | ~8–10GB |
| MPS      | 部分支持  | 视硬件情况而定 |

*实际性能取决于具体硬件配置。*

---

## 📂 项目结构

```
openocr-engine/
├── app_simple.py
├── model_adapter.py
├── config.py
├── hybrid_ocr_engine.py
├── app_api.py
├── templates/
├── uploads/
└── outputs/
```

---

## 🔧 安装方式

```bash
pip install transformers==4.46.3 tokenizers==0.20.3
pip install torch torchvision
pip install flask pillow einops addict matplotlib
```

---

## ▶ 启动方式

```bash
python app_simple.py
```

访问地址：

```
http://localhost:5003
```

---

## 🧪 示例应用场景

可将以下文档：

* 合同文件
* 招标文件
* 扫描 PDF
* 商务文档

转换为结构化 Markdown 输出。

---

## ⚖ 重要法律声明

OpenOCR-Engine 是一个独立的工程项目。

本仓库：

* 不分发 DeepSeek 预训练权重
* 不重新发布原始源码
* 不修改模型架构
* 不声明模型所有权

使用者必须：

* 从官方渠道获取原始模型
* 遵守 DeepSeek 原始 License
* 尊重上游知识产权

本项目仅提供运行时工程封装与部署框架。

---

## 📜 License 说明

本仓库（OpenOCR-Engine）采用 MIT License 发布。

但需注意：

DeepSeek-OCR-2 的模型代码与权重受其原始 License 约束。

本项目不覆盖或替代上游 License 条款。

使用者需同时遵守：

* 本仓库的 MIT License
* DeepSeek 原始 License

---

## 🤝 贡献

欢迎提交 Pull Request。

如果你觉得本项目有帮助，请为仓库点亮 ⭐ Star。

---


# ✅ 截图展示区
<img width="1763" height="881" alt="image" src="https://github.com/user-attachments/assets/cbce282c-f89e-451e-a850-c08161a3883a" />


