# Awesome-Elastic-Data-Warehouse-Compute

# Awesome-Elastic-Data-Warehouse-Compute

**Top Elastic Data Warehouse Compute (Opensource) 🌟 Star if you like it! 🌟**



**Curated List of SaaS Products & Open-Source GitHub Projects**

*Focused on Virtual Warehouses, Concurrency Scaling, Serverless Compute & Self-Hosted Elastic Engines*

**Last updated: November 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Elastic Data Warehouse Compute**. These tools enable organizations to scale analytical compute elastically—decoupling storage from processing power, isolating workloads, and paying only for what they use—from fully managed virtual warehouses with per-second billing to open-source engines that can be deployed on elastic infrastructure.



**Examples** include Snowflake Virtual Warehouses, Amazon Redshift Concurrency Scaling, Databricks SQL Serverless, Google BigQuery Slots, Firebolt Engines, Starburst Galaxy Clusters, ClickHouse Clusters, Dremio Engines, Presto on AWS, and Trino Cloud (the category leaders in commercial and open-source space).



**Open-source emphasis**: This section is expanded with every relevant project for self-hosted elastic compute, MPP engines, and open query infrastructure. **Critical note**: True open-source elastic compute is achieved through the engines themselves—**Trino**, **ClickHouse**, and **Apache Doris** all support elastic scaling when deployed on Kubernetes or cloud infrastructure. The elasticity is an infrastructure concern, not a feature of the engine binary. No open-source project provides the fully managed per-second billing of Snowflake or BigQuery, but for teams willing to operate clusters, the engines are production-proven.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## Sector Overview & Market Dynamics

The global cloud data warehousing and analytical compute market was estimated at approximately $7.5B–$13.3B (2024–2025) and is projected to expand at a CAGR of 22%–26%, driven by migrations from legacy monolithic appliances to decoupled lakehouse architectures. The sector features an oligopolistic, highly concentrated tier at the top where hyperscalers (AWS, Google Cloud, Microsoft) and specialized platform leaders (Snowflake, Databricks) capture roughly 68%+ of aggregate revenue, while remaining moderately fragmented across an active long-tail of high-performance OLAP engines (ClickHouse, Firebolt) and federated query fabrics (Starburst, Dremio).

## SaaS/Hosted Platforms

| Platform | Company Valuation / Revenue | Starting Tier Pricing | Free Tier / Trial Limits | Description |
| :--- | :--- | :--- | :--- | :--- |
| **Amazon Redshift Concurrency Scaling** | ~$2.48T Market Cap (Amazon) / ~$600B+ Rev | **$0.543/hour** (billed per second matching primary node rates, e.g., `ra3.large` on-demand; Serverless from **$0.375/RPU-hour** / $1.50/hr minimum 4-RPU base) | **1 hour free scaling/day per active cluster** (accumulates up to 30 hours); Redshift Serverless offers **90-day trial with $300 credits** (or 2-month 750 hrs/month `dc2.large` provisioned trial) | Automatic compute scaling for concurrent queries with decoupled compute isolation. |
| **Google BigQuery Slots** | ~$2.32T Market Cap (Alphabet) / ~$350B+ Rev | **$0.04/slot-hour** (Standard Edition, US multiregion, autoscale baselines) or **$6.25 per TB** scanned on on-demand | **1 TB of query data processed per month forever free**; Google Cloud free trial grants **$300 credits for 90 days** | Autoscaling query compute units with decoupled storage-compute isolation and commitment discounts. |
| **Databricks SQL Serverless** | ~$134B Valuation / ~$4.8B+ ARR (Dec 2025) | **$0.70/DBU** (Serverless SQL Compute, inclusive of cloud infrastructure costs; 2X-Small warehouse consumes ~1 DBU/hr) | **14-day free trial with up to $400 in usage credits** (plus forever-free restricted Databricks Free Edition for personal non-commercial learning) | Fully managed elastic lakehouse SQL engine on serverless infrastructure with near-instant spin-up. |
| **Snowflake Virtual Warehouses** | ~$75B Market Cap / ~$3.63B Rev (FY2025) | **$2.00/credit** (Standard Edition AWS US East, billed per second with 60s minimum; X-Small = 1 credit/hour = **$2.00/hour**) | **30-day free trial with $400 usage credits** (no credit card required for standard signup) | Independent virtual warehouse clusters with strict workload isolation and per-second autosuspension/resumption. |
| **Starburst Galaxy Clusters** | ~$3.35B Valuation / ~$100M+ ARR | **$0.50/credit** (Pro Tier; cluster costs scale per credit hour based on coordinator/worker sizing) | **3 clusters forever free**; includes **30-day free trial with $500 usage credits** (access to Warp Speed and fault-tolerant execution) | Fully managed, production-grade Trino clusters with autoscaling and cross-cloud federated query capability. |
| **ClickHouse Cloud Clusters** | ~$2.00B Valuation (Series B) / VC-backed | **$0.2181/compute unit/hour** (Basic tier; 1 Compute Unit = 2 vCPU + 8 GiB RAM, billed per minute; ~$0.22/hour) | **30-day free trial with $300 usage credits** (no forever-free tier; automatically lapses unless converted to paid) | Serverless ClickHouse deployment with shared-nothing speed, scale-to-zero compute, and decoupled cloud object storage. |
| **Dremio Engines** | ~$2.00B Valuation (Series E) / VC-backed | **$0.20/DCU-hour** (Dremio Cloud pay-as-you-go; Extra Small engine consumes 32 DCUs/hr = **$6.40/hour**) | **30-day free trial with $400 usage credits** on Dremio Cloud (plus forever-free Community Edition for self-managed Kubernetes/Docker) | Apache Iceberg-native query engines for lakehouse analytics with engine auto-start/stop and replica scaling. |
| **Firebolt Engines** | ~$1.40B Valuation (Series C) / VC-backed | **$0.92/hour** (Small compute-optimized engine running 4 FBUs/hr; compute billed per second, pass-through S3 storage) | **30-day free trial with $200 usage credits** (scale-to-zero compute supported on trial) | Sub-second real-time analytics data warehouse with isolated multi-engine compute and scale-to-zero pricing. |

## Open-Source GitHub Projects



- **Trino**

  **Distributed SQL query engine** (Apache 2.0) — **the standard for elastic federated query**, scalable to thousands of nodes when deployed on Kubernetes or cloud infrastructure. **Features**: **ANSI SQL**; **federation** across S3, Hive, Cassandra, MySQL, and more; **highly parallel distributed execution**; works with BI tools including Tableau, Power BI, and Superset; **Kubernetes-native** deployment for elastic scaling. **Tech stack**: Java. **Deploy**: Self-hosted (Kubernetes, Docker) or Starburst Galaxy. **Trade-off**: **Elasticity is an infrastructure concern**—you scale the cluster, not the engine itself. **Best for**: organizations needing federated queries across disparate sources with the ability to scale compute elastically on Kubernetes.



- **ClickHouse**

  **Column-oriented database for real-time analytics** (Apache 2.0) — **the fastest engine for single-table aggregation**, with **shared-nothing clusters** that scale horizontally. **Features**: **MergeTree engine family**; **vectorized execution**; **replication and sharding** for distributed deployments; **ClickHouse Cloud** adds compute-compute separation and scale-to-zero. **Tech stack**: C++. **Deploy**: Self-hosted clusters or ClickHouse Cloud. **Trade-off**: **Weak JOIN performance**; **not for high-frequency updates**; elastic scaling requires cluster management. **Best for**: log analytics and read-heavy aggregation where horizontal scaling is needed—especially when deployed on Kubernetes with auto-scaling node pools.



- **Apache Doris**

  **MPP analytical database** (Apache 2.0) — **the most balanced open-source MPP engine** for real-time and batch analytics, with **integrated or decoupled storage-compute** architectures. **Features**: **Decoupled storage-compute** for elastic scaling—compute nodes can be added or removed independently of storage; **sub-second latency** with 10,000+ QPS concurrency; **materialized views**; **MySQL protocol**. **Tech stack**: C++, Java. **Deploy**: Self-hosted (integrated or decoupled) or cloud. **Trade-off**: **Lake integration less mature than StarRocks**; decoupled architecture adds operational complexity. **Best for**: teams wanting elastic compute without sacrificing real-time analytics performance—especially those needing both batch and streaming workloads on one engine.



- **StarRocks**

  **High-performance MPP database** (Apache 2.0, Linux Foundation) — **the performance leader for multi-table joins and lakehouse queries**, with **shared-data architecture** for elastic compute. **Features**: **Shared-data mode**—compute nodes (CN) cache hot data while object storage holds persistence, enabling independent compute scaling; **Multi-Catalog** reads Iceberg/Hudi/Delta directly; **asynchronous materialized views**. **Tech stack**: C++, Java. **Deploy**: Self-hosted (shared-nothing or shared-data). **Trade-off**: **Acceleration layer, not source of truth**; elastic scaling in shared-data mode requires object storage configuration. **Best for**: teams with lakehouse architecture needing elastic compute for join-heavy BI queries—especially those wanting independent scaling of compute and storage.



- **Velox**

  **C++ vectorized execution engine** (Apache 2.0) — **the execution layer that makes Presto and Spark faster**, with **elastic scaling inherited from the host engine**. **Features**: **Vectorized execution** for modern CPUs; **connector architecture**; **used by Presto C++** (Velox-Presto) and **Spark's Photon**; **native performance** for single-node workloads. **Tech stack**: C++. **Deploy**: Embedded in host engines. **Trade-off**: **Execution library, not a complete engine**—you need Presto or Spark for SQL parsing, planning, and cluster management. **Best for**: teams wanting native-speed execution within their existing Presto or Spark deployments.



### Additional Strong Open-Source Options



- **Apache Druid** — Real-time analytics database (Apache 2.0). Time-series optimized with sub-second queries; elastic scaling via historical and broker nodes. **Note**: Specialized for event data, not general-purpose warehouse. **Best for**: operational dashboards on streaming data.

- **Apache Pinot** — Real-time distributed OLAP datastore (Apache 2.0). Powering user-facing analytics at LinkedIn and Uber; sub-second queries at high concurrency. **Note**: Operational complexity for elastic scaling. **Best for**: user-facing analytics needing millisecond latency.



**Frameworks for building custom systems**: Combine **Trino** for federated query with **ClickHouse** for real-time aggregation and **Apache Doris** for decoupled storage-compute—creating an elastic query stack on Kubernetes. **None of these match Snowflake's managed per-second billing or BigQuery's serverless slots**, but for teams willing to operate infrastructure, the engines are production-proven at scale.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, license (for open-source), and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Elastic compute platforms handling enterprise data must comply with data protection regulations (GDPR, CCPA, etc.) and implement appropriate access controls.

- **The "managed virtual warehouse" vs. "concurrency scaling" vs. "serverless compute" vs. "slot-based" vs. "self-hosted elastic engine" distinction is critical.** **Snowflake** provides **independent virtual warehouses**—workloads are fully isolated but you pay for running warehouses even when idle . **Redshift Concurrency Scaling** adds **automatic clusters** for concurrent queries, with 1 hour/day free . **Databricks SQL Serverless** is **fully managed serverless** at **$0.70/DBU** . **BigQuery Slots** are **capacity units** with break-even above 50 slots . **Firebolt** offers **per-second billing with scale-to-zero** . **Starburst Galaxy** provides **managed Trino clusters** with 3 free clusters . **Self-hosted engines (Trino, ClickHouse, Doris, StarRocks)** require **Kubernetes or cloud infrastructure** for elasticity. **Choose based on whether you need managed per-second billing, automatic concurrency scaling, serverless simplicity, or self-hosted control.**

- **Snowflake's oversizing risk is the most expensive mistake.** An X-Large costs **4× a Medium** for the same schedule—**8 hours/day of X-Large at Standard costs ~$7,680/month vs. ~$1,920 for Medium** . **Monitor warehouse sizing weekly.**

- **Redshift Concurrency Scaling's 1 hour/day free** covers **97% of customers**—if your spikes are infrequent, you may never pay . **If you have sustained high concurrency, model the overage.**

- **BigQuery's break-even is 50 slots.** At **$0.06/slot-hour on Enterprise**, 100 slots running continuously costs **~$4,380/month**, roughly equivalent to scanning **700 TiB on-demand** . **Query `INFORMATION_SCHEMA.JOBS` for actual slot-milliseconds before committing.**

- **Firebolt's scale-to-zero is genuine**—compute bills per second and stops when idle . **The trade-off**: storage costs continue at object storage rates.

- **Starburst Galaxy's 3 free clusters** are the most generous managed Trino offering . **Pro at $0.50/credit** is competitive for production.

- **ClickHouse Cloud's compute unit pricing** requires sizing modeling—**1 unit = 8 GiB RAM + 2 vCPU**, billed per minute .

- Self-hosted open-source solutions require proper infrastructure (Kubernetes for elastic scaling, object storage for shared-data architectures), security hardening, and ongoing maintenance. **Elastic compute clusters execute against production data**—ensure your deployment meets your organization's security and performance requirements before migrating production workloads.



---



**Made for data engineers, platform architects, and organizations building transparent elastic compute solutions.**

Let's make Elastic Data Warehouse Compute more open, data-driven, and elasticity-aware.
