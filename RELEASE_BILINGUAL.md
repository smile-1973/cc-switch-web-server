# CC Switch Web Server Migration Package

## English

This release package provides a headless `cc-switch-web` server for Linux and SSH-only environments. It is designed for remote servers without a desktop GUI.

### What Is Included

- Prebuilt Linux x86_64 binary: `bin/cc-switch-web`
- Source code for rebuilding: `web-server/`
- Deployment guide: `DEPLOY_WEB_SERVER.md`
- Updated project documentation

### Quick Start

```bash
tar -xzf cc-switch-web-server-migration-20260508.tar.gz
cd cc-switch-3.14.1-server
./bin/cc-switch-web --host 0.0.0.0 --port 7860 --token mypassword
```

Open in your browser:

```text
http://SERVER_IP:7860/?token=mypassword
```

### Security Notes

- Default host is `127.0.0.1`.
- Use `--token` when binding to `0.0.0.0`.
- Persistent configuration is stored under `~/.cc-switch/config.json`.
- Directory permission is enforced as `700`.
- Config file permission is enforced as `600`.
- Ephemeral mode keeps API keys in memory only.
- The server does not write API keys to `/etc/environment`, `/etc/profile`, `~/.bashrc`, `~/.zshrc`, or `/usr/local/bin`.

### Claude Code Temporary Environment

```bash
source <(./bin/cc-switch-web export-env)
claude
```

Or:

```bash
./bin/cc-switch-web exec -- claude
```

### Rebuild On Server

If the included binary is not compatible with your server:

```bash
cd web-server
cargo build --release
./target/release/cc-switch-web --host 0.0.0.0 --port 7860 --token mypassword
```

---

# CC Switch Web 服务迁移包

## 中文

这个发布包提供了一个无桌面依赖的 `cc-switch-web` 服务端，适用于 Linux 服务器、远程 SSH 环境、没有 GUI 桌面的机器。

### 包内包含

- 已编译的 Linux x86_64 可执行文件：`bin/cc-switch-web`
- 可重新构建的源码：`web-server/`
- 部署说明：`DEPLOY_WEB_SERVER.md`
- 已更新的项目文档

### 快速启动

```bash
tar -xzf cc-switch-web-server-migration-20260508.tar.gz
cd cc-switch-3.14.1-server
./bin/cc-switch-web --host 0.0.0.0 --port 7860 --token mypassword
```

浏览器打开：

```text
http://服务器IP:7860/?token=mypassword
```

### 安全说明

- 默认监听地址是 `127.0.0.1`。
- 如果使用 `--host 0.0.0.0`，请务必同时设置 `--token`。
- 持久配置保存到当前用户的 `~/.cc-switch/config.json`。
- 配置目录权限会自动设置为 `700`。
- 配置文件权限会自动设置为 `600`。
- 临时模式只把 API Key 保存在内存中。
- 服务不会把 API Key 写入 `/etc/environment`、`/etc/profile`、`~/.bashrc`、`~/.zshrc` 或 `/usr/local/bin`。

### Claude Code 临时环境

```bash
source <(./bin/cc-switch-web export-env)
claude
```

或者：

```bash
./bin/cc-switch-web exec -- claude
```

### 在服务器上重新构建

如果内置二进制与你的服务器不兼容：

```bash
cd web-server
cargo build --release
./target/release/cc-switch-web --host 0.0.0.0 --port 7860 --token mypassword
```
