# StreamFröst

**StreamFröst** is a decentralized framework for the collaborative creation and execution of cross-organizational data stream processing pipelines. It enables multiple organizations to jointly design, share, and run streaming pipelines while preserving each participant's data sovereignty.

## Demo Video

A demonstration of the system is available at **https://youtu.be/AJ531UAugJc**.

## Motivation

Many real-world streaming applications — smart cities, industrial supply chains, collaborative research — require integrating data across organizational boundaries. Existing stream processing systems are designed for single administrative domains and do not support sovereign, ad-hoc cross-organizational sharing of streams and processing logic. StreamFröst addresses this gap by providing a ready-to-deploy, federated platform that combines user-friendly pipeline editing with fine-grained data access control.

## Architecture

StreamFröst is built on top of three open-source components: **Apache StreamPipes** (pipeline editor and processing engine), **Apache Kafka** (high-throughput data exchange), and the **Solid framework** (decentralized, policy-governed storage). The system is organized in seven layers:

| Layer | Responsibility |
|---|---|
| **Application** | Extended StreamPipes UI for collaborative pipeline editing; federated data source and function catalogs |
| **Federation** | Solid Pod-based decentralized storage for pipeline definitions, policies, and partner metadata; synchronized federated catalogs |
| **Information** | RDF data model and vocabulary for pipelines, data streams, functions, and their schemas |
| **Processing** | Translates pipeline definitions into executable adapters, processors, and sinks; applies stream policies at execution time |
| **Infrastructure** | Physical sensors, compute nodes, and networking infrastructure of each organization |
| **Cross-organizational** | Communication and high-speed data exchange gateways between organizations, bridging pipeline fragments via Kafka topics |
| **Coordination** | Federation service spanning all layers; orchestrates storage, execution distribution, and inter-organizational data exchange |

When a shared pipeline is executed, it is automatically fragmented along organizational boundaries. Each fragment runs locally within its assigned organization, with cross-fragment connections realized as Kafka topics. Organizations retain control over which processing steps they execute and which data they expose.

## Repository Contents

This repository contains the code needed to reproduce the demo presented at DEBS 2026, covering: partner management, pipeline creation and sharing, operator assignment, pipeline fragmentation and execution, cross-organizational data exchange, and federated data and function catalogs.

## Publications

If you use StreamFröst in your work, please cite:

> Liam Tirpitz, Jannis Tölle, Roman Bobekh, Sakshi Gupta, Divyashree Sreenivasa, Usha Tella, Maximilian Breuer, and Sandra Geisler. **Demo: StreamFröst: Collaborative Definition and Execution of Cross-Organizational Stream Processing Pipelines.** In *The 20th ACM International Conference on Distributed and Event-based Systems (DEBS '26)*, June 23–26, 2026, Lisbon, Portugal. ACM. https://doi.org/10.1145/3809481.3816721

The underlying architecture is described in detail in:

> Liam Tirpitz and Sandra Geisler. **Cross-organizational data stream management using solid data spaces.** In *Proc. of the 9th Workshop on Stream processing, Stream-based AI & Stream Data Management in Big Data (co-located with IEEE BigData 2025)*. https://doi.org/10.1109/BigData66926.2025.11401437

## Acknowledgments

Funded by the Deutsche Forschungsgemeinschaft (DFG) under Germany's Excellence Strategy – EXC-2023 Internet of Production – 390621612, and by the Federal Ministry of Research, Technology and Space under grant number 16IS25009.
