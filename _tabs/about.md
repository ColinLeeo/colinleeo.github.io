---
# the default layout is 'page'
icon: fas fa-info-circle
order: 4
---

🧑‍💻 About me

I currently work at Timecho as a database kernel engineer.

I received my master's degree from the [School of Software, Tsinghua University](https://www.thss.tsinghua.edu.cn/), and my bachelor's degree in [Information and Communication Engineering from Beijing University of Posts and Telecommunications](https://sice.bupt.edu.cn/).

I am interested in database systems, with a focus on storage, query optimization, and scheduling, and I am actively involved in the evolution of open-source databases and file formats. My current work centers on Apache IoTDB and Apache TsFile, with a focus on time-series database kernels, file format design, system performance optimization, and database system support for AI workloads.

🚀 Current Projects and Explorations

- [Apache IoTDB](https://github.com/apache/iotdb) -- Apache IoTDB Committer. I mainly work on time-series database kernel development, with interests in storage engines, query processing, system performance optimization, and the engineering evolution of IoTDB for industrial time-series data scenarios.

- [Apache TsFile](https://github.com/apache/tsfile) -- Apache TsFile PMC Member. I continue to participate in TsFile community building, releases, and technical evolution, focusing on the application of time-series file formats in cross-language implementations, embedded and analytical workloads, query performance optimization, and AI workloads. Recently, I have been working on integrating TsFile with AI and analytical database ecosystems, including TsFile data access support in Hugging Face datasets, the inclusion of TsFile in Hugging Face file formats, and TsFile read/write support in DuckDB.

📄 Papers and Blogs

- Jianyang Gao, Yutong Gou, Yuexuan Xu, Jifan Shi, Yongyi Yang, **Shuolin Li**, Raymond Chi-Wing Wong, Cheng Long. [Revisiting RaBitQ and TurboQuant: A Symmetric Comparison of Methods, Theory, and Experiments](https://arxiv.org/abs/2604.19528) -- Accepted by VLDB Vector Workshop. This work revisits RaBitQ and TurboQuant under a unified and symmetric framework, comparing the two methods in terms of methodology, theoretical guarantees, and experimental results.

📜 Past Projects

- [RaBitQ_TurboQuant_KV_Comparison](https://github.com/VectorDB-NTU/RabitQ_TurboQuant_KV_Comparison) -- A comparative research project on RaBitQ and TurboQuant, supporting the paper *Revisiting RaBitQ and TurboQuant: A Symmetric Comparison of Methods, Theory, and Experiments*. The project provides a unified experimental framework for comparing the two methods in vector quantization, approximate nearest neighbor search, and key-value cache scenarios.

- [TuGraphDB](https://github.com/TuGraph-family/tugraph-db) -- Designed a metadata encoding scheme to resolve update anomalies caused by the original encoding method, enabling metadata modifications with O(1) complexity.

- [Apache HAWQ commercial version a.k.a. OushuDB](https://github.com/apache/hawq) -- Implemented resource and cluster virtualization to support multi-tenancy and affinity-based query scheduling.

- [Benchmark for Multi-Language TsFile](https://github.com/ColinLeeo/TsFile-BenchMark) -- A configurable performance benchmarking tool for TsFile across multiple programming languages. It supports scheduled execution and continuous monitoring, with results periodically reported to the TsFile community via GitHub issues.

- [SIMD_TS2DIFF](https://github.com/ColinLeeo/SIMD_TS2DIFF) -- A vectorized decoding approach for the core encoding/decoding method in TsFile, incorporating block-level filtering with bit-packing. This design improves time-range query performance by up to two orders of magnitude.

- [MiniGU](https://github.com/TuGraph-family/miniGU) -- Contributed to the development of a Rust-based embedded graph database with GQL support, aimed at educational and research use in universities, while exploring native graph-vector integration for future RAG systems.

- LoadaWise-ORCA-for-NewHardwareDB -- Designed load-aware query optimization and scheduling methods in the ORCA optimizer framework, targeting multi-model databases on emerging hardware platforms.

📰 News

- 2026.08.22: Gave a talk titled *Apache TsFile and the AI Ecosystem* as a speaker at the [2026 Time Series Tech Innovation Summit](https://www.timecho-global.com/2026-summit/).
- The TsFile file format was accepted by Hugging Face.
- The TsFile file format was accepted by the DuckDB community extension ecosystem.
- The paper [Revisiting RaBitQ and TurboQuant: A Symmetric Comparison of Methods, Theory, and Experiments](https://arxiv.org/abs/2604.19528) was accepted by VLDB Vector Workshop.
- Became an Apache TsFile PMC Member.
- Released TsFile C / C++ / Python V2.1.0 as Release Manager.
- Became an Apache TsFile Committer.
- Became an Apache IoTDB Committer.
- Recognized as TuGraph Core Contributor of the Year by the community.
