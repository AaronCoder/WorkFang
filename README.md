# WorkFang

WorkFang 是基于开源 Agent Operating System **OpenFang** 的企业化发行与扩展版本，目标是构建适合企业场景的自主 Agent（Autonomous Agent）系统，让 Agent 更贴近业务、部署更简单、管理更可控。

## 目录

- [项目定位](#项目定位)
- [核心能力](#核心能力)
- [架构说明](#架构说明)
- [终端与用户模式](#终端与用户模式)
- [快速开始](#快速开始)
- [文档导航](#文档导航)
- [与 OpenFang 的关系](#与-openfang-的关系)
- [开发与贡献](#开发与贡献)
- [许可证](#许可证)

## 项目定位

1. WorkFang 基于开源 Agent Operating System OpenFang 开发，旨在创建适合企业的自主 Agent（Autonomous Agent），实现贴近业务的简化操作。
2. 架构上，WorkFang 提供企业管理的配置服务器，通过安全服务将组织配置项下发到各客户端，为 Agent 执行提供统一配置与管控能力。
3. 终端以 Desktop App 形式提供，简化安装和配置。默认采用终端用户模式（End User Mode）；Super User 在完成鉴权后可切换到 Power User 模式进行配置。

## 核心能力

- 企业级 Agent 运行底座：继承 OpenFang 的 Agent OS 能力。
- 组织级配置中心：集中管理组织配置并安全下发到终端。
- Desktop 优先体验：降低一线用户的安装与配置门槛。
- 双层用户权限模型：默认 End User，授权后进入 Power User。
- 面向业务场景：通过预置与可配置能力，减少手工操作路径。

## 架构说明

WorkFang 采用“中心化配置管理 + 终端执行”的架构：

- 配置服务器（Enterprise Config Server）
- 安全配置分发服务（Secure Delivery Service）
- Desktop 客户端（内置 Agent 运行与执行能力）

典型流程：

1. Super User 在企业侧完成配置管理。
2. 配置服务器通过安全服务向组织终端下发配置项。
3. Desktop 客户端拉取并应用配置。
4. 本地 Agent 按组织策略执行任务并反馈状态。

## 终端与用户模式

### End User Mode（默认）

- 面向业务终端用户。
- 提供开箱即用的 Agent 使用体验。
- 隐藏复杂系统配置，降低误操作风险。

### Power User Mode（鉴权切换）

- 仅 Super User 鉴权通过后可用。
- 用于高级配置、策略调整与组织级管理操作。
- 与默认模式隔离，确保日常使用稳定性。

## 快速开始

> 当前仓库保留 OpenFang 原生工程结构。若你是首次接触，建议先阅读 OpenFang 原始 README 与文档。

### 1) 获取代码

```bash
git clone <your-workfang-repo-url>
cd WorkFang
```

### 2) 本地构建（Rust Workspace）

```bash
cargo build --workspace
```

### 3) 运行测试（可选）

```bash
cargo test --workspace
```

### 4) 启动与运行

WorkFang 在当前阶段沿用 OpenFang 的核心运行方式。具体初始化、启动和 CLI 细节请参考下方链接：

- OpenFang README: https://github.com/RightNow-AI/openfang/blob/main/README.md

## 文档导航

项目文档目录：`docs/`

- `docs/getting-started.md`
- `docs/architecture.md`
- `docs/configuration.md`
- `docs/cli-reference.md`
- `docs/security.md`
- `docs/desktop.md`

总览入口：`docs/README.md`

## 与 OpenFang 的关系

WorkFang 以 OpenFang 为技术底座进行企业化增强。为避免信息分叉，底层能力与通用使用方式优先参考 OpenFang 官方文档：

- OpenFang README: https://github.com/RightNow-AI/openfang/blob/main/README.md
- OpenFang Docs: https://openfang.sh/docs

## 开发与贡献

- 贡献指南：`CONTRIBUTING.md`
- 变更记录：`CHANGELOG.md`
- 安全策略：`SECURITY.md`

提交变更前建议执行：

```bash
cargo fmt --all
cargo clippy --workspace --all-targets -- -D warnings
cargo test --workspace
```

## 许可证

本项目当前沿用仓库内许可证文件：

- `LICENSE-MIT`
- `LICENSE-APACHE`
