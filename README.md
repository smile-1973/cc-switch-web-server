# CC Switch Web Server

## English

Headless web management server for CC Switch on Linux/SSH-only servers.

Download the migration archive from `dist/`:

```bash
tar -xzf dist/cc-switch-web-server-migration-20260508.tar.gz
cd cc-switch-3.14.1-server
./bin/cc-switch-web --host 0.0.0.0 --port 7860 --token mypassword
```

Open:

```text
http://SERVER_IP:7860/?token=mypassword
```

See `RELEASE_BILINGUAL.md` and `DEPLOY_WEB_SERVER.md` for details.

---

# CC Switch Web 服务端

## 中文

适用于 Linux 服务器和纯 SSH 环境的 CC Switch 无桌面 Web 管理服务。

从 `dist/` 下载迁移包：

```bash
tar -xzf dist/cc-switch-web-server-migration-20260508.tar.gz
cd cc-switch-3.14.1-server
./bin/cc-switch-web --host 0.0.0.0 --port 7860 --token mypassword
```

浏览器打开：

```text
http://服务器IP:7860/?token=mypassword
```

详细说明见 `RELEASE_BILINGUAL.md` 和 `DEPLOY_WEB_SERVER.md`。
