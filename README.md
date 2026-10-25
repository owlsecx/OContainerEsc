# 🦉 OContainerEsc

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-Security-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0-cyan?style=flat-square"/>
</p>

> **OContainerEsc** — part of the OwlSec Toolkit.

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OContainerEsc helps you harden your own containers by finding configurations that would let a workload break out to the host. It audits docker/podman inspect JSON, compose and Kubernetes manifests, or the container it is running in, and reports each risk with the escape path, a fix and the matching MITRE ATT&CK technique. It only audits and never attempts an escape.

---

## ✨ Features

- Checks 17 escape vectors: privileged mode, CAP_SYS_ADMIN, hostPID/Net/IPC, docker.sock, device mounts, missing seccomp/AppArmor, /proc mounts and more
- Scans docker/podman inspect JSON, docker-compose, Kubernetes manifests and Dockerfiles
- Self-audit of the current environment: container detection, capabilities, mounts, cgroups and sensitive host paths
- Graded findings with escape path, remediation and ATT&CK mapping (T1611 and related)
- Escape-vector catalog with per-vector explanations and a vulnerable demo config generator
- Reports in TXT / JSON / Markdown / CSV / SARIF; exits with code 3 on CRITICAL/HIGH findings

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OContainerEsc                              # interactive menu
docker inspect mycontainer | ./OContainerEsc --scan -
./OContainerEsc --manifest deployment.yaml
./OContainerEsc --self
./OContainerEsc --catalog
```

Run `./OContainerEsc --help` for the full list of options.

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
