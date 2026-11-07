### Hi, I'm Bikram 👋

M.Tech CSE student at **IIIT Delhi**. I build **systems, AI applications and data pipelines from
the bottom up**: query engines, consensus, network stacks and container runtimes; LLM agents and an
MLOps platform; streaming and batch analytics. The systems projects are tested in CI and measured
against the established system they imitate: DuckDB, the Raft paper's guarantees, Linux's TCP,
Flannel and hnswlib.

### ⚙️ Systems

| Project | What it is | Stack |
|---|---|---|
| [**morsel**](https://github.com/vik-bit/morsel) | Vectorized, columnar query engine: AVX2 kernels with runtime CPU dispatch, hash joins and aggregation, morsel-driven parallelism. **8 TPC-H queries give exactly DuckDB's answers** at SF 1, and the engine is benchmarked against DuckDB, with the caveats stated | C++17 · SIMD · sanitizers |
| [**ballot**](https://github.com/vik-bit/ballot) | Raft consensus and a linearizable key-value store: a deterministic simulator that replays any failure from a seed, **20,000 randomized fault schedules, every history linearizable** (Porcupine), real processes under `kill -9` and iptables partitions, and mutation testing that catches 9 of 10 planted bugs | Go · Raft · Jepsen-style testing |
| [**ustack**](https://github.com/vik-bit/ustack) | TCP/IP stack in user space on a TAP device: ARP, IPv4, ICMP, and TCP with SACK, Reno, CUBIC and HyStart++. You can `ping` and `curl` it. **Matches the Linux kernel's TCP throughput at 1% loss** on the same `tc netem` path (the ranges overlap) | Go · TCP · Linux networking |
| [**minirun**](https://github.com/vik-bit/minirun) | Container runtime and Kubernetes CNI plugin on raw Linux primitives: namespaces, cgroups v2, a hand-assembled seccomp filter, veth and bridges. **The only CNI of a 3-node cluster, matching Flannel in the same routing mode** (24 Gbit/s pod to pod) | Go · Linux · Kubernetes |
| [**vecdex**](https://github.com/vik-bit/vecdex) | HNSW approximate nearest-neighbour index written from scratch, with AVX2/NEON distance kernels picked at runtime and Python bindings. **Same recall as hnswlib on SIFT1M**, benchmarked against hnswlib and FAISS, and used as PolicyPilot's vector search | C++17 · SIMD · Python bindings |

Also: [Kubernetes CNI benchmarks](https://github.com/vik-bit/GROUP6_GRSPROJECT): Calico and Flannel compared on a Kind cluster under Locust load (led a team of 5)

### 🤖 AI & ML

| Project | What it is | Stack |
|---|---|---|
| [**PolicyPilot**](https://github.com/vik-bit/policypilot) | Agentic RAG that maps new regulations to the policy clauses they affect, drafts the changes and verifies every quote. The agent beats a no-AI baseline (96% vs 50% correct impact labels; **McNemar p = 0.0002**), with a pre-registered evaluation, real Indian regulations and prompt-injection tests. A pre-registered ablation dropped the reranker: **26× faster search at 10,000 clauses**, and higher recall at every library size above 1,000 clauses | Python · LLM agents · hybrid search |
| [**MLOps Platform**](https://github.com/vik-bit/mlops-platform) · [live](https://mlops-frontend-5smr.onrender.com/) · **🚧 ongoing** | Train, deploy and monitor ML models from one web console: dataset upload, async training queued through Redis, MLflow tracking, model serving with SHAP explanations, PSI/KS drift detection, and an LLM copilot that answers from 15 live platform APIs. Six microservices behind a JWT gateway, deployed on Render. **In development since April 2026**; latest: per-column feature engineering with **leak-free target encoding** (a CI test shows the naive version scoring 76% accuracy on pure noise, this one 50%) | Python · FastAPI · MLflow · Next.js |
| [**APIShift**](https://github.com/vik-bit/apishift) · [demo PR](https://github.com/vik-bit/apishift-demo/pull/1) | Agent that migrates code across breaking library upgrades (pandas 1→2): a type-inferring scanner, AST codemods, LLM fixes that must pass the project's own tests, then a pull request. **25/25 on its 28-case benchmark**, against 44% for codemods alone, and also scored on cases taken from real open-source fixes | Python · AST · LLM agents |
| [**medscribe**](https://github.com/vik-bit/medscribe) | Clinical speech-to-note on PriMock57 consultations. LoRA fine-tuning of Whisper-small in a plain PyTorch loop cut held-out **WER from 15.2% to 9.5%** (paired 95% CI −7.0 to −4.4 points; adapter released). Plus a multi-agent note writer built from scratch with a grounding verifier, compared honestly with a single agent: it removed every lexically ungrounded claim but used 5× the prompt tokens and did not write better notes | Python · PyTorch · Hugging Face · LLM agents |

### 📊 Data engineering

| Project | What it is | Stack |
|---|---|---|
| [**Taxi stream analytics**](https://github.com/vik-bit/kafka-taxi-stream-analytics) | Kafka pipeline that replays NYC taxi trips and checks streaming sketches (Bloom filters, reservoir sampling, HyperLogLog, DGIM, MinHash-LSH) against exact answers on the same stream. Measures partitioning, consumer scaling and lag: **HyperLogLog stays near 2% error at 11,200 events/s** | Python · Kafka · streaming algorithms |
| [**MapReduce vs Spark vs DuckDB**](https://github.com/vik-bit/nyc-taxi-mapreduce-spark-duckdb) | The same NYC taxi workloads (up to 2M trips) on three engines with measured timings, and when each one fits. For example, a 2M-row join takes ~6.6 s in Spark and **~0.12 s in DuckDB** on one laptop | Python · Spark · DuckDB · mrjob |

**How I work:** I build with AI coding agents, mostly Claude Code, which wrote much of the code in
my recent projects. I choose the problems and the designs, and I don't take a result on trust: every
headline number is checked against a reference system by tests that run in CI, and each README
says what was measured, what wasn't, and the bugs that testing found.

**Also:** Tech lead on [RecipeDB 3.0](https://cosylab.iiitd.edu.in/recipedb3) (IIIT Delhi research) · frontend intern at
Be10x AI (a code editor used by 600K+ learners) · Codeforces [1563](https://codeforces.com/profile/BikiByte)

**Tools:** C++17 · Go · Python · SIMD (AVX2, NEON) · Linux internals · TCP/IP · distributed consensus · Docker · Kubernetes · PyTorch · Hugging Face · FastAPI · Kafka · Spark · PostgreSQL
