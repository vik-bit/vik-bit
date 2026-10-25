### Hi, I'm Bikram 👋

M.Tech CSE student at **IIIT Delhi**. I build **systems and AI infrastructure from the bottom
up**: query engines, vector search, consensus, network stacks, container runtimes, and the LLM
applications on top. My main projects are tested in CI and measured against the established
system they imitate: DuckDB, hnswlib, FAISS, Flannel, runc and the Linux kernel's TCP.


**AI systems**

| Project | What it is | Stack |
|---|---|---|
| [**PolicyPilot**](https://github.com/vik-bit/policypilot) | Agentic RAG that maps new regulations to the policy clauses they affect, drafts the changes and verifies every quote. The agent beats a no-AI baseline (100% vs 85% precision, 96% vs 50% impact labels; **McNemar p = 0.0002**), with a pre-registered evaluation, a held-out set of real Indian regulations and prompt-injection tests | Python · LLM agents · hybrid search · FastAPI |
| [**APIShift**](https://github.com/vik-bit/apishift) · [demo PR](https://github.com/vik-bit/apishift-demo/pull/1) | Agent that migrates code across breaking library upgrades (pandas 1.x → 2.x): a static analyser with dataflow type inference, exact AST codemods, and LLM fixes accepted only when the project's own tests pass. **Fixed 25/25 benchmark cases vs 44% for codemods alone and 96% for the LLM alone**, with 22% fewer tokens, and opened a verified pull request on a live repo | Python · static analysis · LLM agents · GitHub Actions |
| [**MLOps Platform**](https://github.com/vik-bit/mlops-platform) · [live](https://mlops-frontend-5smr.onrender.com/) | Train, deploy and monitor ML models, with experiment tracking, drift detection and an LLM copilot that answers from live platform data | Python · MLflow · Docker · TypeScript |



**Systems**

| Project | What it is | Stack |
|---|---|---|
| [**morsel**](https://github.com/vik-bit/morsel) | Vectorized, columnar query engine: AVX2 kernels with runtime CPU dispatch, hash joins and aggregation, morsel-driven parallelism. **8 TPC-H queries give exactly DuckDB's answers** at SF 1, and the engine is benchmarked against DuckDB, with the caveats stated | C++17 · SIMD · sanitizers |
| [**vecdex**](https://github.com/vik-bit/vecdex) | HNSW vector search engine from scratch, with SIMD distance kernels and parallel graph construction. **Same recall as hnswlib and FAISS on SIFT1M** (0.999 recall@10). Its benchmarks exposed a race in parallel builds, fixed and checked with ThreadSanitizer | C++17 · AVX2 / NEON · pybind11 |
| [**ballot**](https://github.com/vik-bit/ballot) | Raft consensus and a linearizable key-value store, tested like a distributed system should be: a deterministic simulator that replays any failure from a seed, **20,000 randomized fault schedules (18.2M operations), every history linearizable** (Porcupine), real processes under `kill -9` and iptables partitions, and mutation testing that shows the tests catch 9 of 10 planted bugs | Go · Raft · Jepsen-style testing |
| [**ustack**](https://github.com/vik-bit/ustack) | TCP/IP stack in user space on a TAP device: ARP, IPv4, ICMP, and TCP with SACK, Reno, CUBIC and HyStart++. You can `ping` and `curl` it. Over the same `tc netem` path it **matches the Linux kernel's TCP throughput at 1% loss** (103–104% of the median; the ranges overlap) | Go · TCP · Linux networking |
| [**minirun**](https://github.com/vik-bit/minirun) | Container runtime and Kubernetes CNI plugin on raw Linux primitives: namespaces, cgroups v2, a hand-assembled seccomp filter, veth and bridges. **The only CNI of a 3-node cluster, matching Flannel in the same routing mode** (24 Gbit/s pod to pod) | Go · Linux · Kubernetes |



**Data**

| Project | What it is | Stack |
|---|---|---|
| [**Kafka Stream Analytics**](https://github.com/vik-bit/kafka-taxi-stream-analytics) | Replays NYC taxi trips through Kafka and checks streaming sketches (Bloom, HyperLogLog, DGIM, MinHash-LSH) against exact answers as partitions, keys and producer speed change | Python · Kafka |
| [**Spark vs MapReduce vs DuckDB**](https://github.com/vik-bit/nyc-taxi-mapreduce-spark-duckdb) | The same analytics workloads on three engines, with measured timings | Python · Spark · DuckDB |
| [**Kubernetes CNI benchmarks**](https://github.com/vik-bit/GROUP6_GRSPROJECT) | Led a team of 5 benchmarking Flannel, Calico and Cilium on Kind and bare-metal clusters | Kubernetes · Python |

**Also:** Tech lead on [RecipeDB 3.0](https://cosylab.iiitd.edu.in/recipedb3) (IIIT Delhi research) · frontend intern at
Be10x AI (a code editor used by 600K+ learners) · Codeforces [1563](https://codeforces.com/profile/BikiByte)

**Tools:** C++17 · Go · Python · TypeScript · SIMD (AVX2, NEON) · Linux internals · TCP/IP · distributed consensus · Docker · Kubernetes · FastAPI · MLflow · Kafka · Spark · PostgreSQL · AWS
