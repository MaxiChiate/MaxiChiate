<h1 align="center">Hey, I'm Maxi 👋</h1>

<p align="center">
  <b>Software Engineering @ ITBA 🇦🇷 · Exchange @ DTU 🇩🇰</b><br>
  I like the layers most people abstract away.
</p>

<div align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&weight=500&size=20&duration=2600&pause=900&color=38BDF8&center=true&vCenter=true&width=680&lines=Cloud+%7C+DevOps+%7C+Infrastructure;Kubernetes%2C+Open+vSwitch+%26+VXLAN+overlays;Writing+a+kernel+from+the+bootloader+up;Non-blocking+sockets+in+plain+C;Storage+nobody+can+read+but+you" alt="Typing SVG" />
</div>

<p align="center">
  <a href="https://linkedin.com/in/maximo-chiatellino-72277b36b">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  <a href="mailto:chiatellinomaximo@gmail.com">
    <img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
  </a>
</p>

---

## 💫 About me

I'm into **cloud, DevOps, networking and Linux**: how packets actually move between pods, what a scheduler does when you're not looking, and how to keep a deploy boring.

- 🌐 Built virtual network topologies with namespaces, veth pairs, **Open vSwitch** and **VXLAN** at DTU
- 🐧 Wrote an x86-64 kernel with a scheduler, buddy allocator, semaphores and pipes
- 🚀 Ship a production platform for a law firm with CI/CD on GitHub Actions
- 📚 Currently studying Terraform, Helm, Kubernetes on AWS, gRPC and Kafka

---

## 🏝️ Thesis: Archipelagus

> **Distributed custody of clinical records between health institutions that don't need to trust each other.**

Argentina's health sector has been hit by ransomware, mass data leaks and single-vendor breaches exposing dozens of clinics at once. Archipelagus lets institutions **back each other up** on a shared storage grid where **nobody can read what they host for others**, and no central operator holds data, keys or power.

```mermaid
flowchart LR
    subgraph A["🏥 Institution A (trusted boundary)"]
        UI[Web app] --> API[App server]
        API --> KC[Keycloak · OIDC + 2FA]
        API --> BAO[OpenBao · master key]
        API --> PG[(PostgreSQL · hash-chained audit)]
        API --> GW[Tahoe-LAFS gateway]
    end
    GW -- "encrypted, erasure-coded shares only" --> GRID
    subgraph GRID["🌊 Consortium storage grid"]
        N1[Node A]
        N2[Node B]
        N3[Node C]
    end
    GRID -. governed by quorum .-> M[📜 Consortium manifest]
```

- 🔐 Files are **encrypted client-side** and **erasure-coded** before leaving the institution
- 🧩 Shares are dispersed across nodes that can't read or rebuild them
- 🗳️ The consortium is governed by a **committee deciding by quorum**; one breach stays inside one institution
- 🧱 Stack: Tahoe-LAFS · Keycloak · OpenBao · PostgreSQL · Celery + Redis

---

## 🛠️ Things I've built

| | Project | What's inside |
|---|---|---|
| 🧦 | [**POROTOS: SOCKS5 proxy**](https://github.com/MatiasColeur/TP-PROTOS) | Non-blocking SOCKS5 server in C (RFC 1928/1929): selector multiplexer, state machine, IPv4/IPv6/FQDN, auth, and a custom TCP admin API with live metrics |
| 🐧 | [**x86-64 kernel**](https://github.com/MaxiChiate/TP2-SO) | Bare-metal OS on QEMU: process scheduler, buddy memory manager, semaphores, IPC, syscalls and a userland shell, built inside Docker |
| ☸️ | **Kubernetes cluster networking** *(DTU)* | Multi-node cluster with CNI pod networking and service discovery, Ansible-automated provisioning, OVS + VXLAN multi-tenant overlays |
| ⚽ | [**Fulbito**](https://github.com/MaxiChiate/Fulbito) | Sports facility booking platform: Java 21 + Spring REST API, TypeScript SPA, PostgreSQL with PL/pgSQL-enforced booking rules, JWT |
| ⚖️ | [**Estudio Candame**](https://github.com/MaxiChiate/estudio_candame_php) | Freelance production platform turning an intake form into filing-ready incorporation paperwork. Ported from Spring/Kotlin to PHP 8.3, deployed via GitHub Actions |
| 🧠 | [**AI Systems**](https://github.com/MaxiChiate/SIA-TPs) | Search algorithms on Sokoban, genetic algorithms, neural networks |
| 🍃 | [**MongoDB & Redis**](https://github.com/gonzasharif/TPO-BD2) | Dockerized Mongo + Redis stack with automated CSV ingestion and indexing |

---

## 💻 Tech stack

<div align="center">

### ☁️ Cloud & Infra
![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Ansible](https://img.shields.io/badge/ansible-%231A1918.svg?style=for-the-badge&logo=ansible&logoColor=white)
![OpenStack](https://img.shields.io/badge/OpenStack-ED1944?style=for-the-badge&logo=openstack&logoColor=white)
![Terraform](https://img.shields.io/badge/terraform-%235835CC.svg?style=for-the-badge&logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazonwebservices&logoColor=white)

### 🐧 Systems & Networking
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Bash](https://img.shields.io/badge/bash-%23121011.svg?style=for-the-badge&logo=gnu-bash&logoColor=white)
![C](https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white)
![Open vSwitch](https://img.shields.io/badge/Open%20vSwitch-2E3440?style=for-the-badge&logo=linuxfoundation&logoColor=white)
![QEMU](https://img.shields.io/badge/QEMU-FF6600?style=for-the-badge&logo=qemu&logoColor=white)

### 🔁 CI/CD
![GitHub Actions](https://img.shields.io/badge/github%20actions-%232671E5.svg?style=for-the-badge&logo=githubactions&logoColor=white)
![GitLab CI](https://img.shields.io/badge/gitlab%20ci-%23181717.svg?style=for-the-badge&logo=gitlab&logoColor=white)
![Jenkins](https://img.shields.io/badge/jenkins-%232C5263.svg?style=for-the-badge&logo=jenkins&logoColor=white)
![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)

### ⚙️ Backend
![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring](https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![PHP](https://img.shields.io/badge/php-%23777BB4.svg?style=for-the-badge&logo=php&logoColor=white)
![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white)

### 🗄️ Data
![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=for-the-badge&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/redis-%23DD0031.svg?style=for-the-badge&logo=redis&logoColor=white)
![MySQL](https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white)

</div>

---

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/MaxiChiate/MaxiChiate/output/snake-dark.svg" />
  <img src="https://raw.githubusercontent.com/MaxiChiate/MaxiChiate/output/snake.svg" alt="Contribution snake" />
</picture>
<sub>🇦🇷 Spanish (native) · 🇬🇧 English (advanced) · Buenos Aires</sub>

</div>
