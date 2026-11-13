# Awesome-Relational-Database-Cloud-Backup

# Awesome Relational Database Cloud Backup

> A curated list of top Relational Database Cloud Backup platforms — both SaaS/Hosted commercial enterprise data protection solutions and open-source alternatives for backing up SQL Server, Oracle, PostgreSQL, MySQL, and other relational databases to the cloud.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Druva Database Backup](#druva-database-backup)
  - [Veeam Backup & Replication](#veeam-backup--replication)
  - [Commvault Database Backup](#commvault-database-backup)
  - [Cohesity Database Protection](#cohesity-database-protection)
  - [Rubrik Database Protection](#rubrik-database-protection)
  - [Bacula Enterprise](#bacula-enterprise)
- [Open-Source Software](#-open-source-software)
  - [DBackup](#dbackup)
  - [Portabase](#portabase)
  - [pgBackRest](#pgbackrest)
  - [Barman](#barman)
  - [Holland Backup](#holland-backup)
  - [Percona XtraBackup](#percona-xtrabackup)
  - [mariabackup](#mariabackup)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Relational Database Backup platforms. These are not open-source but are included as reference points for feature comparison.

### Druva Database Backup
**Type:** SaaS data protection with MS-SQL and SAP HANA support
Druva provides cloud-native backup for Microsoft SQL Server databases, supporting Full, Differential, and Transaction Log backups with configurable schedules and retention policies [citation:1]. Log backups can be scheduled at intervals from 5 to 120 minutes, with retention handled separately from weekly/monthly/yearly policies [citation:1]. Druva also supports SAP HANA backup with full, delta, incremental, differential, log, and catalog backups, allowing continued use of native HANA tools for restore [citation:9]. The platform is fully managed SaaS, eliminating infrastructure overhead.

### Veeam Backup & Replication
**Type:** Enterprise backup with application-consistent database protection
Veeam provides application-consistent backups for Microsoft SQL Server, PostgreSQL, and Oracle Database natively, alongside support for Azure SQL databases and Azure Cosmos DB accounts [citation:2]. Dedicated Veeam Plug-Ins deliver transactionally-consistent database-level backups for Oracle RMAN (Oracle-certified), SAP HANA (SAP-certified), Microsoft SQL Server, IBM Db2, SAP MaxDB, and MongoDB replica sets [citation:10]. This makes Veeam one of the most comprehensive commercial options for heterogeneous database environments.

### Commvault Database Backup
**Type:** Enterprise data protection with 50+ database support
Commvault supports over 50 databases including Microsoft SQL Server, Oracle, SAP HANA, MongoDB, Cassandra, CockroachDB, Apache Iceberg, and cloud databases like AWS RDS and GCP Cloud SQL [citation:3]. The platform emphasizes cyber recovery capabilities alongside traditional backup, with IntelliSnap and oplog-based incremental backups for MongoDB [citation:3]. Commvault Cloud also extends to Azure Database workloads including Azure SQL, MySQL, MariaDB, PostgreSQL, and Cosmos DB [citation:11].

### Cohesity Database Protection
**Type:** Unified data security with database-native integration
Cohesity provides database protection for Oracle (web-scale Oracle-certified), Microsoft SQL Server (native integration), MongoDB, Cassandra, Hadoop, and SAP [citation:4]. The platform emphasizes instant recovery at scale and unified data security management, positioning database backup as part of a broader cyber-resilient data platform.

### Rubrik Database Protection
**Type:** Vendor-agnostic physical and virtual database protection
Rubrik supports Oracle (standalone, RAC, and ASM configurations), Microsoft SQL Server, MySQL, PostgreSQL, SAP HANA, MongoDB, and Cassandra through its Elastic App Service [citation:5]. The platform allows database administrators to leverage preferred management tools while providing backup and recovery through VSS integration for Windows-based databases [citation:5]. Rubrik emphasizes vendor-agnostic protection across operating systems, databases, hypervisors, clouds, and SaaS applications.

### Bacula Enterprise
**Type:** Enterprise open-source backup with dedicated database plugins
Bacula Enterprise provides dedicated plugins for MySQL (Dump and Binary mode with Point-in-Time Recovery), PostgreSQL (hot backup with WAL files), MS SQL (full and differential via VSS), and Oracle (block-level with RMAN SBT API) [citation:7][citation:15]. The MySQL plugin supports Percona XtraBackup for hot backups and Mariabackup for MariaDB 10.1+ [citation:15]. While the core is open-source, database plugins are commercial Enterprise features.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Relational Database Backup tools. The open-source ecosystem spans **full database backup automation platforms**, **PostgreSQL-specific backup solutions**, **MySQL/MariaDB hot backup tools**, and **lightweight self-hosted managers**.

### DBackup
**Stack:** Node.js / Docker / S3-compatible storage | **License:** Open Source (GitHub)
DBackup is a self-hosted database backup automation tool with a modern Web UI, supporting PostgreSQL (12-18), MySQL (5.7-9.x), MariaDB (10.x-11.x), MongoDB (4.x-8.x), Redis, Valkey, SQLite, Microsoft SQL Server (2017-2022, Azure SQL Edge), Azure SQL Database (beta), and Firebird (beta) [citation:6]. Key features include **RBAC with granular permissions**, **2FA/Passkeys**, an **encrypted credential vault** for SSH keys and API tokens, configurable rate limits, a **REST API** for automation, and **Docker-ready multi-arch images** (AMD64/ARM64) [citation:6]. Backups can be stored to S3, FTP, or local storage with cron scheduling and notifications.
**Best for:** Teams wanting a modern, self-hosted backup manager covering multiple relational and NoSQL databases with strong security features and Docker deployment.

### Portabase
**Stack:** Self-hosted (Docker/Kubernetes/CLI) | **License:** Open Source (non-profit)
Portabase is an open-source, self-hosted tool for automating database backups and on-demand restores, supporting PostgreSQL, MySQL, MariaDB, MongoDB, Redis, Valkey, SQLite, Firebird, MSSQL Server, and Docker Volumes [citation:14]. Key features include **AES-GCM encryption**, **GFS retention policies** (hourly/daily/weekly/monthly/yearly), backup scheduling via cron, **REST API and MCP server** for automation, and notifications via email, Slack, Discord, Telegram, and webhooks [citation:14]. The dashboard does not contact agents directly, so deployments do not need inbound ports opened where databases reside [citation:14]. Storage options include S3-compatible services, Google Drive, Azure Blob, SFTP, and Rclone backends. Governed by a French non-profit association [citation:14].
**Best for:** Organizations wanting a French-governed, self-hosted backup platform with broad database coverage, encryption, and strong automation capabilities.

### pgBackRest
**Stack:** C / PostgreSQL | **License:** Open Source
pgBackRest is a backup and restore solution for PostgreSQL designed to scale to large databases and workloads [citation:14]. It is the de facto standard for PostgreSQL-specific backup in production environments, supporting full, differential, and incremental backups, parallel processing, compression, encryption, and cloud storage backends (S3, GCS, Azure). Its maturity and performance make it the first choice for PostgreSQL-only environments.

### Barman
**Stack:** Python / PostgreSQL | **License:** Open Source
Barman (Backup and Recovery Manager) is an open-source administration tool for disaster recovery of PostgreSQL servers, written in Python. It supports remote backups of multiple servers, retention policies, WAL archiving, and point-in-time recovery. Barman is maintained by EnterpriseDB and is widely deployed in PostgreSQL-centric organizations.

### Holland Backup
**Stack:** Python | **License:** Open Source
Holland is an open-source backup framework originally developed by Rackspace, focused on backing up databases [citation:14]. It provides a pluggable architecture for MySQL, PostgreSQL, and other data sources, with support for various backup methods and storage backends. Holland is positioned for organizations wanting a flexible, extensible Python-based backup framework.

### Percona XtraBackup
**Stack:** C++ | **License:** GPL-2.0
Percona XtraBackup is an open-source hot backup utility for MySQL-based servers that does not lock the database during backup [citation:15]. It supports InnoDB, XtraDB, and MyISAM tables on MySQL and Percona Server, ensuring consistency of the whole backup. It is the industry standard for MySQL hot backups and is used by many managed database services.

### mariabackup
**Stack:** C | **License:** GPL-2.0
mariabackup is the recommended backup tool for MariaDB 10.1 and above, included with MariaDB distributions [citation:15]. It is a fork of Percona XtraBackup adapted for MariaDB, providing hot backup capabilities with support for InnoDB and other storage engines. It is the native choice for MariaDB-specific backup workflows.

---

## 📊 Comparison at a Glance

| Software | License | Stack | SQL Server | Oracle | PostgreSQL | MySQL/MariaDB | Self-Hosted | Best For |
|----------|---------|-------|------------|--------|------------|---------------|-------------|----------|
| **Druva** | Proprietary | Cloud | ✅ | (SAP HANA) | ❌ | ❌ | ❌ | Managed SaaS SQL + HANA |
| **Veeam** | Proprietary | Cloud/On-prem | ✅ | ✅ RMAN | ✅ | (Plug-ins) | (On-prem) | Broadest database coverage |
| **Commvault** | Proprietary | Cloud/On-prem | ✅ | ✅ | ✅ | ✅ | (On-prem) | 50+ databases + cloud |
| **Cohesity** | Proprietary | Cloud/Appliance | ✅ | ✅ | ❌ | ❌ | (Appliance) | Unified data security |
| **Rubrik** | Proprietary | Cloud/Appliance | ✅ | ✅ | ✅ | ✅ | (Appliance) | Vendor-agnostic + VSS |
| **Bacula Ent.** | Commercial | On-prem | ✅ | ✅ | ✅ | ✅ | ✅ | Enterprise open-source + plugins |
| **DBackup** | Open Source | Node.js/Docker | ✅ | ❌ | ✅ | ✅ | ✅ | Modern multi-DB UI + RBAC |
| **Portabase** | Open Source | Docker/K8s | ✅ | ❌ | ✅ | ✅ | ✅ | French-governed + encryption |
| **pgBackRest** | Open Source | C | ❌ | ❌ | ✅ | ❌ | ✅ | PostgreSQL production standard |
| **Percona XtraBackup** | GPL-2.0 | C++ | ❌ | ❌ | ❌ | ✅ MySQL | ✅ | MySQL hot backup standard |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Relational Database Cloud Backup tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem **splits** between **full multi-database backup automation platforms** (DBackup, Portabase) that provide a unified UI and scheduling across many engines, and **database-specific hot backup tools** (pgBackRest for PostgreSQL, Percona XtraBackup for MySQL, mariabackup for MariaDB) that are the production standards for their respective engines. **DBackup** and **Portabase** are the most notable open-source efforts to provide a commercial-like management experience across heterogeneous database environments [citation:6][citation:14]. Commercial platforms like Veeam and Commvault remain far more capable for enterprise-scale Oracle RMAN, SAP HANA, and hybrid cloud workloads with certified plug-ins and cyber recovery features [citation:3][citation:10].

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
