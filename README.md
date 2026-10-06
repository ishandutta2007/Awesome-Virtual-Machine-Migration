# Awesome-Virtual-Machine-Migration

## Top Virtual Machine Migration Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Hypervisor Migration, Cloud Workload Mobility & Open-Source V2V Tools*  

**Last updated: October 2026**



This repository tracks notable **commercial VM migration platforms** and **open-source projects** that move virtual machines between hypervisors, clouds, and on-premises infrastructure. These tools handle disk conversion, driver injection, and cutover orchestration — enabling organizations to escape vendor lock-in, migrate to cloud, or modernize virtualization stacks.



**Examples** include AWS Server Migration Service, Azure Migrate, Google Migrate for Compute Engine, Carbonite Migrate, Zerto, Veeam, CloudEndure, PlateSpin Migrate, Nutanix Move, and Commvault (the category leaders).



**Open-source emphasis**: VM migration is a strong open-source domain. **virt-v2v** remains the foundational V2V tool, continuously developed since 2007 . **Coriolis** provides cloud migration as a service . **Migration Manager** brings a modern web interface for VMware-to-Incus migrations . **hyper2kvm** delivers production-ready migration with Kubernetes operator support . **OpenNebula OneSwap** handles VMware-to-KVM with in-place conversion . This section is heavily expanded.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[AWS Server Migration Service](https://aws.amazon.com/server-migration-service/)**  

  AWS's agentless migration service for VMware vSphere, Hyper-V, and Azure VMs to AWS. **Incremental replication with minimal downtime** — automates the migration of live servers to Amazon EC2.



- **[Azure Migrate](https://azure.microsoft.com/en-us/products/azure-migrate/)**  

  **Microsoft's comprehensive migration hub** — discovery, assessment, and migration for servers, databases, and web apps. **Agentless VMware migration** with dependency analysis and cost estimation .



- **[Google Migrate for Compute Engine](https://cloud.google.com/migrate/compute-engine)**  

  Google's VM migration service for VMware, AWS, and Azure to GCP. **Streaming replication with test clones** for validation before cutover.



- **[Carbonite Migrate](https://www.carbonite.com/migrate/)**  

  **Real-time replication and migration** for physical, virtual, and cloud workloads. **Minimal downtime cutover** with continuous data protection.



- **[Zerto](https://www.zerto.com/)**  

  **The enterprise standard for IT resilience and migration** — continuous replication, orchestration, and automated failover. **The reference for disaster recovery and cloud migration** .



- **[Veeam](https://www.veeam.com/)**  

  **Backup and replication platform with migration capabilities** — VMware, Hyper-V, and cloud workloads. **The most widely deployed backup solution** with migration features.



- **[CloudEndure](https://www.cloudendure.com/)**  

  **AWS's disaster recovery and migration service** (acquired by AWS). **Continuous block-level replication** for live migration with minimal downtime.



- **[PlateSpin Migrate](https://www.microfocus.com/en-us/products/platespin-migrate/overview)**  

  **Micro Focus's workload migration** — physical, virtual, and cloud migrations across heterogeneous environments.



- **[Nutanix Move](https://www.nutanix.com/products/move)**  

  **Nutanix's migration tool** — VMware ESXi, Hyper-V, and AWS to Nutanix AHV. **Agentless migration** with automated driver injection .



- **[Commvault](https://www.commvault.com/)**  

  **Enterprise data management with migration capabilities** — backup, recovery, and cloud migration.



## Open-Source GitHub Projects



- **[virt-v2v](https://github.com/libguestfs/virt-v2v)**  

  **The foundational open-source V2V conversion tool**, GPL-2.0 licensed . **Converts guests from VMware, Xen, Hyper-V, and other hypervisors to run on KVM** — managed by libvirt, OpenStack, oVirt, or other targets . **Continuously developed since 2007** — the reference implementation for guest conversion . **Modifies guests to make them bootable on KVM and installs virtio drivers** for performance . **Companion tool virt-p2v** virtualizes physical machines via bootable ISO/CD/PXE . **Trade-off**: VDDK public downloads ended September 2026 — migration tools must use alternative transport paths . **Best for direct V2V conversion to KVM** .



- **[h2kvm](https://github.com/zyvorai/h2kvm)**  

  **Any hypervisor → KVM migration toolchain**, open-source . **No VDDK dependency** — disks leave through vSphere API and NFS, then convert offline . **Offline guest fixes for VirtIO, GRUB, and Windows bootloader before power-on** . **Includes GuestKit** for disk inspection before boot, **Zorvia** for KubeVirt VM management, **Zeus OS** for visual infrastructure, and **Machina** as libvirt control plane . **PyPI package**: `pip install "h2kvm==1.2.1"` . **Best for VDDK-free VMware migration with offline guest repair** .



- **[Coriolis](https://github.com/cloudbase/coriolis)**  

  **Cloud Migration as a Service platform**, Apache-2.0 licensed . **Migrates VMs, templates, storage, and networking between clouds** — VMware vSphere, SCVMM, Azure, AWS, OpenStack, and GCP . **Automatically injects drivers and tools** — cloud-init/cloudbase-init for OpenStack, LIS kernel modules for Hyper-V and Azure . **Uses Oslo libraries with OpenStack-style architecture** — stateless microservices, queues, and scalability from the start . **Authentication via Keystone** with secrets stored in Barbican . **API-driven** with Postman collection available . **Best for cloud-to-cloud and on-prem-to-cloud migrations** .



- **[Migration Manager (FuturFusion)](https://github.com/FuturFusion/migration-manager)**  

  **Modern instance migration tool for VMware → Incus**, Apache-2.0 licensed . **Runs as a service with REST API, CLI, and web interface** . **Add sources (vCenter/ESXi) and targets (Incus clusters), query instances, override VM sizing, define batches, and track migrations in background** . **v0.6.15** (August 2026) with active development . **Best for VMware-to-Incus migrations** .



- **[hyper2kvm](https://github.com/ssahani/hyper2kvm)**  

  **Enterprise-grade VM migration toolkit**, LGPL-3.0 licensed . **Production-ready v1.0.0** with 96.8% success rate and 2-3x faster than traditional tools . **Kubernetes Operator (v1.6.0)** with Helm chart, admission webhooks, and 20+ Prometheus metrics . **480+ VMCraft API methods** with 90%+ test coverage . **Includes GuestKit** — pure-Rust VM disk inspection with AI-powered diagnostics for pre-migration validation . **GitHub Actions and GitLab CI integration** . **Best for enterprise-scale migration with Kubernetes orchestration** .



- **[OpenNebula OneSwap](https://github.com/OpenNebula/one-swap)**  

  **Migrate VMware workloads to OpenNebula/KVM**, open-source . **In-place conversion on datastore** — no local copy, terabyte disks work on workers with small local storage . **Runs virt-v2v-in-place to install virtio drivers and fix initramfs/bootloader** . **`--shift-skip-morph` for guests virt-v2v rejects** (e.g., Alpine) that boot unmodified . **Minimum permissions for standard conversions** . **Best for OpenNebula migrations with large disks** .



- **[EuroMigrator Engine](https://hub.docker.com/r/euromigrator/engine)**  

  **Enterprise cloud migration to sovereign EU providers**, open-source . **47 cloud services across 7 providers** — AWS, Azure, GCP to European alternatives . **AI-powered migration planning and risk assessment** . **Real-time replication with zero-downtime cutover** . **GDPR compliant** with encryption at rest and transit . **Multi-arch** (amd64/arm64) . **Best for EU data sovereignty migrations** .



- **[xmigrate](https://hub.docker.com/r/xmigrate/xmigrate)**  

  **Open-source infrastructure migration tool**, CC BY-NC-ND 4.0 licensed . **DC to DC, DC to cloud, cloud to DC, and cloud to cloud** VM migration . **Agentless discovery and migration** to AWS, GCP, and Azure . **Environment discovery, automatic network creation, and multi-disk support** . **FastAPI, Ansible, and PostgreSQL stack** . **Best for simple cloud migrations with discovery** .



- **[Libvirt/QEMU Live Migration](https://ubuntu.com/server/docs/explanation/virtualisation/live-migration/)**  

  **The foundational open-source live migration capability** . **QEMU streams VM memory and CPU state; libvirt coordinates** the handoff between hosts . **Versioned machine types and CPU baselines** enable migration across heterogeneous infrastructure . **`host-model` CPU mode** automatically builds compatible CPU definitions . **Best for KVM-to-KVM live migration** .



### Additional Strong Open-Source Options



- **oVirt** — Open-source virtualization management with migration capabilities  .

- **Proxmox VE** — Built-in migration for VMs and containers .

- **Harvester** — HCI with VM migration support  .

- **OpenStack Nova** — Live migration with parallel memory transfer (Gazpacho 2026.1) and vTPM support  .

- **KubeVirt** — VM management on Kubernetes with migration capabilities  .

- **Transiva** — NFC-based VMware disk export without VDDK  .

- **GuestKit** — Rust-based VM disk inspection for pre-migration validation  .



**Frameworks for building custom VM migration solutions**: Combine **virt-v2v** as the foundational conversion engine . Use **h2kvm** for VDDK-free migration with offline guest repair . Deploy **Coriolis** for cloud-to-cloud and on-prem-to-cloud migrations with driver injection . Choose **Migration Manager** for VMware-to-Incus with modern web interface . Use **hyper2kvm** for enterprise-scale migration with Kubernetes operator . Integrate **GuestKit** for pre-migration disk inspection . Note that true enterprise migration with continuous replication, automated failover, and vendor-supported SLAs (Zerto, Veeam, CloudEndure) remains primarily commercial territory; open-source stacks provide strong conversion, cloud migration, and live migration foundations that require integration for complete enterprise deployment.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- VM migration involves moving critical workloads and data. **Test migrations in isolated environments first** — driver issues, bootloader problems, and driver signing failures can cause boot loops .

- **VDDK public downloads ended September 2026** — tools relying on VMware's Virtual Disk Development Kit must use alternative transport paths (NFS, HTTPS) .

- **Windows Server 2025 migration requires specific configurations** — UEFI/q35 machine type and CPU passthrough are required for successful boot . Virtio driver signing issues can cause reboot loops .

- **Open-source migration tools require operational expertise** — disk conversion, driver injection, and cutover orchestration are complex. Plan for testing and rollback capabilities.

- The open-source ecosystem provides strong conversion, cloud migration, and live migration foundations, but **continuous replication, automated failover, and vendor-supported SLAs** remain primarily commercial offerings.



---



**Made for infrastructure architects, cloud engineers, and organizations seeking VM migration sovereignty.**  

Let's make virtual machine migration more open, transparent, and accessible.
