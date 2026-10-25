### Hi, I'm Bikram 👋

M.Tech CSE student at **IIIT Delhi**. I build **systems and AI infrastructure from the bottom
up**: query engines, consensus, network stacks, container runtimes, and the LLM applications on
top. Each project is tested in CI and measured against the established system it imitates.

**Featured projects**

| Project | What it is | Stack |
|---|---|---|
| [**morsel**](https://github.com/vik-bit/morsel) | Vectorized, columnar query engine: AVX2 kernels with runtime CPU dispatch, hash joins and aggregation, morsel-driven parallelism. **8 TPC-H queries give exactly DuckDB's answers** at SF 1, and the engine is benchmarked against DuckDB, with the caveats stated | C++17 · SIMD · sanitizers |
| [**ballot**](https://github.com/vik-bit/ballot) | Raft consensus and a linearizable key-value store: a deterministic simulator that replays any failure from a seed, **20,000 randomized fault schedules, every history linearizable** (Porcupine), real processes under `kill -9` and iptables partitions, and mutation testing that catches 9 of 10 planted bugs | Go · Raft · Jepsen-style testing |
| [**ustack**](https://github.com/vik-bit/ustack) | TCP/IP stack in user space on a TAP device: ARP, IPv4, ICMP, and TCP with SACK, Reno, CUBIC and HyStart++. You can `ping` and `curl` it. **Matches the Linux kernel's TCP throughput at 1% loss** on the same `tc netem` path (the ranges overlap) | Go · TCP · Linux networking |
| [**minirun**](https://github.com/vik-bit/minirun) | Container runtime and Kubernetes CNI plugin on raw Linux primitives: namespaces, cgroups v2, a hand-assembled seccomp filter, veth and bridges. **The only CNI of a 3-node cluster, matching Flannel in the same routing mode** (24 Gbit/s pod to pod) | Go · Linux · Kubernetes |
| [**PolicyPilot**](https://github.com/vik-bit/policypilot) | Agentic RAG that maps new regulations to the policy clauses they affect, drafts the changes and verifies every quote. The agent beats a no-AI baseline (96% vs 50% correct impact labels; **McNemar p = 0.0002**), with a pre-registered evaluation, real Indian regulations and prompt-injection tests | Python · LLM agents · hybrid search |
| [**MLOps Platform**](https://github.com/vik-bit/mlops-platform) · [live](https://mlops-frontend-5smr.onrender.com/) | Train, deploy and monitor ML models from one web console: dataset upload, async training queued through Redis, MLflow tracking, model serving with SHAP explanations, PSI/KS drift detection, and an LLM copilot that answers from 15 live platform APIs. Six microservices behind a JWT gateway, **built April–June 2026** and deployed on Render | Python · FastAPI · MLflow · Next.js |

**More:** [vecdex](https://github.com/vik-bit/vecdex) (HNSW vector search, same recall as hnswlib on SIFT1M) ·
[APIShift](https://github.com/vik-bit/apishift) (pandas 1→2 migration agent, 25/25 on its own 28-case benchmark) ·
[Kafka stream analytics](https://github.com/vik-bit/kafka-taxi-stream-analytics) ·
[Spark vs MapReduce vs DuckDB](https://github.com/vik-bit/nyc-taxi-mapreduce-spark-duckdb) ·
[Kubernetes CNI benchmarks](https://github.com/vik-bit/GROUP6_GRSPROJECT) (led a team of 5)

**How I work:** I build with AI coding agents, mostly Claude Code, which wrote much of the code in
my recent projects. I choose the problems and the designs, and I don't take a result on trust: every
headline number is checked against a reference system by tests that run in CI, and each README
says what was measured, what wasn't, and the bugs that testing found.

**Also:** Tech lead on [RecipeDB 3.0](https://cosylab.iiitd.edu.in/recipedb3) (IIIT Delhi research) · frontend intern at
Be10x AI (a code editor used by 600K+ learners) · Codeforces [1563](https://codeforces.com/profile/BikiByte)

**Tools:** C++17 · Go · Python · SIMD (AVX2, NEON) · Linux internals · TCP/IP · distributed consensus · Docker · Kubernetes · FastAPI · Kafka · Spark · PostgreSQL
