# CC Switch Web Server Deployment

This package contains the headless `cc-switch-web` server for Linux servers.

## Quick Start

```bash
tar -xzf cc-switch-web-server-migration.tar.gz
cd cc-switch-3.14.1-server
./bin/cc-switch-web --host 127.0.0.1 --port 7860
```

For remote browser access, bind to `0.0.0.0` and set a token:

```bash
./bin/cc-switch-web --host 0.0.0.0 --port 7860 --token mypassword
```

Open:

```text
http://SERVER_IP:7860/?token=mypassword
```

## Ephemeral Mode

Use memory-only mode when you do not want keys written to disk:

```bash
./bin/cc-switch-web --ephemeral --host 127.0.0.1 --port 7860
```

## Claude Code Temporary Environment

Persistent mode can export the current provider into the current shell:

```bash
source <(./bin/cc-switch-web export-env)
claude
```

Or run Claude Code with a temporary environment:

```bash
./bin/cc-switch-web exec -- claude
```

## Security Checks

Persistent config is stored under the current user's home directory:

```bash
ls -ld ~/.cc-switch
ls -l ~/.cc-switch/config.json
```

Expected permissions:

```text
~/.cc-switch            700
~/.cc-switch/config.json 600
```

The web server does not write API keys to `/etc/environment`, `/etc/profile`,
`~/.bashrc`, `~/.zshrc`, or `/usr/local/bin`.

## Rebuild On Server

If the included binary does not match your server architecture, rebuild it:

```bash
cd web-server
cargo build --release
../web-server/target/release/cc-switch-web --host 127.0.0.1 --port 7860
```
